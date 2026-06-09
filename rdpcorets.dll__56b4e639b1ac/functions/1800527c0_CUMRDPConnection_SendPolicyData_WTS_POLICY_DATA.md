# CUMRDPConnection::SendPolicyData(_WTS_POLICY_DATA *)

- ea: `0x1800527c0`
- end: `0x1800540b4`
- name: `?SendPolicyData@CUMRDPConnection@@UEAAJPEAU_WTS_POLICY_DATA@@@Z`
- size: `6388`
- prototype: `__int64 __fastcall(CUMRDPConnection *__hidden this, struct _WTS_POLICY_DATA *)`
- caller_count: `0`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800014d8`
- `0x1800015f0`
- `0x1800071c0`
- `0x1800071f0`
- `0x180009628`
- `0x18000e420`
- `0x18000f784`
- `0x180010908`
- `0x180012200`
- `0x180013b88`
- `0x1800172d0`
- `0x1800173e4`
- `0x180022990`
- `0x180022b90`
- `0x1800231f0`
- `0x18003394c`
- `0x180033958`
- `0x180033da0`
- `0x180034970`
- `0x18004bff0`
- `0x1800527c0`
- `0x18014d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180052f71`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180052f89`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180052f71`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180052f89`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18005293d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18005317b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18005293d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18005317b`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180052957`
- `RDPBASE!PAL_System_CritSecEnter` at `0x1800530d7`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180053eba`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180052957`
- `RDPBASE!PAL_System_CritSecEnter` at `0x1800530d7`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180053eba`
- `OLEAUT32!__imp_SysFreeString` at `0x180053235`
- `OLEAUT32!__imp_SysFreeString` at `0x180053235`
- `OLEAUT32!__imp_VariantInit` at `0x180052865`
- `OLEAUT32!__imp_VariantInit` at `0x180052872`
- `OLEAUT32!__imp_VariantInit` at `0x18005287f`
- `OLEAUT32!__imp_VariantInit` at `0x18005288c`
- `OLEAUT32!__imp_VariantInit` at `0x180052896`
- `OLEAUT32!__imp_VariantInit` at `0x1800528a3`
- `OLEAUT32!__imp_VariantInit` at `0x180052fe5`
- `OLEAUT32!__imp_VariantInit` at `0x180052865`
- `OLEAUT32!__imp_VariantInit` at `0x180052872`
- `OLEAUT32!__imp_VariantInit` at `0x18005287f`
- `OLEAUT32!__imp_VariantInit` at `0x18005288c`
- `OLEAUT32!__imp_VariantInit` at `0x180052896`
- `OLEAUT32!__imp_VariantInit` at `0x1800528a3`
- `OLEAUT32!__imp_VariantInit` at `0x180052fe5`
- `OLEAUT32!__imp_VariantClear` at `0x180053138`
- `OLEAUT32!__imp_VariantClear` at `0x180053145`
- `OLEAUT32!__imp_VariantClear` at `0x180053152`
- `OLEAUT32!__imp_VariantClear` at `0x18005315f`
- `OLEAUT32!__imp_VariantClear` at `0x180053169`
- `OLEAUT32!__imp_VariantClear` at `0x180053138`
- `OLEAUT32!__imp_VariantClear` at `0x180053145`
- `OLEAUT32!__imp_VariantClear` at `0x180053152`
- `OLEAUT32!__imp_VariantClear` at `0x18005315f`
- `OLEAUT32!__imp_VariantClear` at `0x180053169`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180052a31`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180052c3d`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180052a31`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180052c3d`

## string_xrefs

- `0x180053e59`: `UMTSLICPlugin`
- `0x180053d9f`: `UMTSInputPlugin`
- `0x180052a5a`: `Failed to allocate Monitor Config`
- `0x180052f4c`: `Local\TS Certificate Update Event`
- `0x1800533d4`: `Failed to create the stream object from endpoint`
- `0x180053441`: `Failed to create the stream object from pipe`
- `0x1800534a9`: `Failed to create the stream object from base stream`
- `0x1800534e0`: `No transport to create a stream from!`
- `0x180053585`: `Failed to create an rdp core connection`
- `0x180053638`: `StackConfig`
- `0x180053674`: `Failed to set the property stack config`
- `0x1800536ab`: `SecurityConfig`
- `0x1800536d4`: `Failed to set the property security config`
- `0x18005370b`: `MonitorConfig`
- `0x180053734`: `Failed to set the property monitor config`
- `0x18005376b`: `ShowProtocolHeaders`
- `0x180053794`: `Failed to set the show protocol headers config`
- `0x180053a32`: `Failed to set UMRDP stack configuration info!`
- `0x180053bfa`: `Failed to create the interface with the License Server`
- `0x180053dc8`: `Failed to get input plugin property form core connection`
- `0x180053dfc`: `UMTSCommandPlugin`
- `0x180053e25`: `Failed to get command plugin property form core connection`
- `0x180053e82`: `Failed to get Licesing plugin property form core connection`

## pseudocode

```c
__int64 __fastcall CUMRDPConnection::SendPolicyData(CUMRDPConnection *this, struct _WTS_POLICY_DATA *a2)
{
  __int64 v2; // r15
  __int64 v3; // rbx
  __int64 v4; // r14
  __int64 v5; // rsi
  __int64 v6; // rdi
  LONGLONG v7; // r13
  GUID v8; // xmm0
  __int64 v9; // r12
  __int64 v10; // rdx
  __int64 v11; // r8
  int v12; // r9d
  CUMRDPConnection *v13; // rax
  bool v14; // zf
  int v15; // r14d
  __int64 v16; // rdx
  __int64 v17; // r8
  CUMRDPConnection *v18; // rbx
  CUMRDPConnection *v19; // r15
  __int64 v20; // rcx
  BSTR v21; // rax
  __int64 v22; // r8
  int v23; // r9d
  _DWORD *v24; // rdx
  __int16 *v25; // rdx
  void *v26; // rax
  struct _WTS_POLICY_DATA *v27; // r8
  int v28; // ecx
  int v29; // eax
  int v30; // ecx
  bool v31; // sf
  CUMRDPConnection *v32; // rax
  int v33; // eax
  int v34; // r8d
  int v35; // r9d
  unsigned __int16 *v36; // rax
  __int64 v37; // rdx
  CUMRDPConnection *v38; // rax
  int v39; // ecx
  int v40; // r9d
  char *v41; // rax
  __int16 *v42; // rdx
  int v43; // ecx
  int v44; // r8d
  int v45; // r9d
  SHORT v46; // ax
  __int64 v47; // rcx
  int v48; // ecx
  int v49; // r9d
  char *v50; // rdx
  void *v51; // rcx
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 v54; // rdx
  __int64 v55; // r8
  void *v56; // rcx
  __int64 v57; // rdx
  __int64 v58; // r8
  __int64 v59; // rdx
  __int64 v60; // r8
  __int64 v61; // rdx
  __int64 v62; // r8
  __int64 v63; // rdx
  __int64 v64; // r8
  __int64 v65; // rdx
  __int64 v66; // r8
  __int64 v67; // rdx
  __int64 v68; // r8
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
  __int64 v79; // rdx
  __int64 v80; // r8
  __int64 v81; // rdx
  __int64 v82; // r8
  __int64 v83; // rdx
  __int64 v84; // r8
  __int64 v85; // rdx
  __int64 v86; // r8
  __int64 v87; // rdx
  __int64 v88; // r8
  __int64 v90; // rdx
  __int64 v91; // r8
  __int64 v92; // r15
  __int64 v93; // rcx
  unsigned __int16 *v94; // r14
  int v95; // eax
  __int64 v96; // r11
  unsigned __int64 v97; // r15
  unsigned __int16 *v98; // rax
  int v99; // eax
  int v100; // r8d
  int v101; // r9d
  int v102; // eax
  int v103; // r8d
  int v104; // r9d
  __int64 v105; // rcx
  __int64 v106; // rcx
  __int64 v107; // rcx
  int v108; // eax
  int v109; // r8d
  int v110; // r9d
  __int64 v111; // rcx
  unsigned __int64 *v112; // [rsp+30h] [rbp-D0h]
  LPCSTR *v113; // [rsp+40h] [rbp-C0h]
  void *p_psz; // [rsp+48h] [rbp-B8h]
  int v115; // [rsp+50h] [rbp-B0h] BYREF
  CUMRDPConnection *v116; // [rsp+58h] [rbp-A8h] BYREF
  struct _WTS_POLICY_DATA *v117; // [rsp+60h] [rbp-A0h] BYREF
  LPCSTR psz; // [rsp+68h] [rbp-98h] BYREF
  const char *v119; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v120; // [rsp+78h] [rbp-88h] BYREF
  CUMRDPConnection *v121; // [rsp+80h] [rbp-80h]
  struct IRDPCollection *v122; // [rsp+88h] [rbp-78h] BYREF
  CUMRDPConnection *v123; // [rsp+90h] [rbp-70h] BYREF
  __int64 v124; // [rsp+98h] [rbp-68h] BYREF
  __int64 v125; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v126; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v127; // [rsp+ACh] [rbp-54h] BYREF
  unsigned int v128; // [rsp+B0h] [rbp-50h] BYREF
  int v129; // [rsp+B4h] [rbp-4Ch] BYREF
  void *v130; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v131; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v132; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v133; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v134; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v135; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v136; // [rsp+E8h] [rbp-18h] BYREF
  BSTR bstrString; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v138; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v139; // [rsp+100h] [rbp+0h] BYREF
  LONGLONG v140; // [rsp+108h] [rbp+8h] BYREF
  __int64 v141; // [rsp+110h] [rbp+10h] BYREF
  __int64 v142; // [rsp+118h] [rbp+18h] BYREF
  __int64 v143; // [rsp+120h] [rbp+20h] BYREF
  __int64 v144; // [rsp+128h] [rbp+28h] BYREF
  __int64 (__fastcall ***v145)(_QWORD, GUID *, __int64 *); // [rsp+130h] [rbp+30h] BYREF
  VARIANTARG v146; // [rsp+138h] [rbp+38h] BYREF
  VARIANTARG v147; // [rsp+150h] [rbp+50h] BYREF
  VARIANTARG pvarg; // [rsp+168h] [rbp+68h] BYREF
  VARIANTARG v149; // [rsp+180h] [rbp+80h] BYREF
  __int64 v150; // [rsp+198h] [rbp+98h] BYREF
  VARIANTARG v151; // [rsp+1A0h] [rbp+A0h] BYREF
  VARIANTARG v152; // [rsp+1B8h] [rbp+B8h] BYREF
  VARIANTARG v153; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE *v154; // [rsp+1F0h] [rbp+F0h] BYREF
  int v155; // [rsp+1F8h] [rbp+F8h]
  const wchar_t *v156; // [rsp+200h] [rbp+100h]
  __int64 v157; // [rsp+208h] [rbp+108h]
  void *Block; // [rsp+248h] [rbp+148h]
  GUID ActivityId; // [rsp+250h] [rbp+150h] BYREF
  _BYTE v160[64]; // [rsp+260h] [rbp+160h] BYREF

  v121 = this;
  v2 = 0;
  v125 = 0;
  v145 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&v152, 0, sizeof(v152));
  memset(&v153, 0, sizeof(v153));
  memset(&v149, 0, sizeof(v149));
  memset(&v147, 0, sizeof(v147));
  v126 = 0;
  memset(&v151, 0, sizeof(v151));
  v129 = 0;
  v127 = 0;
  v128 = 0;
  v117 = a2;
  VariantInit(&pvarg);
  VariantInit(&v152);
  VariantInit(&v153);
  VariantInit(&v149);
  VariantInit(&v147);
  VariantInit(&v151);
  bstrString = 0;
  memset_0(&v154, 0, 0x60u);
  v120 = 0;
  v143 = 0;
  v130 = 0;
  v142 = 0;
  v3 = 0;
  v4 = 0;
  v136 = 0;
  v5 = 0;
  v144 = 0;
  v6 = 0;
  v135 = 0;
  v7 = 0;
  v8 = (GUID)*((_OWORD *)v121 + 45);
  v134 = 0;
  v9 = 0;
  v124 = 0;
  ActivityId = v8;
  v122 = 0;
  v133 = 0;
  v132 = 0;
  v131 = 0;
  v141 = 0;
  v150 = 0;
  v140 = 0;
  v139 = 0;
  v138 = 0;
  EventActivityIdControl(4u, &ActivityId);
  v13 = v121;
  v123 = (CUMRDPConnection *)((char *)v121 + 64);
  if ( *((_DWORD *)v121 + 18) )
  {
    PAL_System_CritSecEnter(*((_QWORD *)v121 + 8), v10, v11);
    v13 = v121;
  }
  v14 = (*((_BYTE *)v13 - 60) & 4) == 0;
  v116 = (CUMRDPConnection *)((char *)v13 - 88);
  if ( !v14 )
  {
    v15 = -2147467260;
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v115 = 5399;
      v120 = (unsigned __int64)"SendPolicyData";
      LODWORD(v117) = -2147467260;
      v119 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
      psz = "SendPolicyData quitting because object is terminated!";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        -2147467260,
        (unsigned int)&byte_18019456F,
        v11,
        v12,
        (__int64)&psz,
        (__int64)&v117,
        (__int64)&v119,
        (__int64)&v115,
        (__int64)&v120);
    }
    goto LABEL_6;
  }
  v20 = *((_QWORD *)v13 + 69);
  if ( v20 )
    (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v20 + 80LL))(v20, L"SendPolicyData");
  v21 = SysAllocStringByteLen(0, 8u);
  pvarg.llVal = (LONGLONG)v21;
  v24 = v21;
  if ( !v21 )
  {
    v15 = -2147024882;
    if ( (unsigned int)dword_1801B76C8 <= 2 )
    {
LABEL_6:
      CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v123);
LABEL_7:
      v18 = v121;
      v19 = v123;
      goto LABEL_64;
    }
    LODWORD(v117) = 5411;
    psz = "Failed to allocate Monitor Config";
    v25 = &word_18019451E;
    v119 = "SendPolicyData";
    v120 = (unsigned __int64)"clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
    v116 = (CUMRDPConnection *)"Error HResult failed";
    p_psz = &psz;
    v113 = &v119;
    v112 = &v120;
    v26 = &v116;
LABEL_13:
    v115 = -2147024882;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      -2147024882,
      (_DWORD)v25,
      v22,
      v23,
      (__int64)v26,
      (__int64)&v115,
      (__int64)v112,
      (__int64)&v117,
      (__int64)v113,
      (__int64)p_psz);
    goto LABEL_6;
  }
  v27 = v117;
  pvarg.vt = 8;
  v28 = *(_DWORD *)v21 ^ (*(_DWORD *)v21 ^ (8 * v117->fDisableEncryption)) & 8;
  *(_DWORD *)v21 = v28;
  v29 = v28 ^ ((unsigned __int8)v28 ^ (unsigned __int8)(v27->fDisableAutoReconnect << 7)) & 0x80;
  *v24 = v29;
  v30 = v29 ^ (v27->ColorDepth ^ v29) & 7;
  *v24 = v30;
  *v24 = v30 ^ ((unsigned __int8)v30 ^ (unsigned __int8)(16 * v27->MinEncryptionLevel)) & 0x70;
  v31 = (*(int (__fastcall **)(_QWORD, const wchar_t *, int *))(**((_QWORD **)v121 + 12) + 32LL))(
          *((_QWORD *)v121 + 12),
          L"SkipLegacyRdp",
          &v129) < 0;
  v32 = v121;
  if ( !v31 && v129 )
    *((_BYTE *)v121 + 524) = 0;
  psz = (char *)v32 + 240;
  v33 = CUMRDPConnection::SSLInfoToSecFilterSettings(
          v116,
          (CUMRDPConnection *)((char *)v32 + 240),
          v117->MinEncryptionLevel,
          (struct RDPENC_SECFILTER_SETTINGS *)&v154);
  v115 = v33;
  if ( v33 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
    {
      v15 = v33;
    }
    else
    {
      v15 = v115;
      v116 = (CUMRDPConnection *)"Failed to initialize sec filter settings";
      LODWORD(v117) = 5436;
      psz = "SendPolicyData";
      v119 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
      v120 = (unsigned __int64)"Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        dword_1801B76C8,
        (unsigned int)byte_1801944CD,
        v34,
        v35,
        (__int64)&v120,
        (__int64)&v115,
        (__int64)&v119,
        (__int64)&v117,
        (__int64)&psz,
        (__int64)&v116);
    }
    goto LABEL_6;
  }
  v36 = SysAllocStringByteLen(psz, 0x120u);
  ATL::CComBSTR::Attach((ATL::CComBSTR *)&bstrString, v36);
  if ( !bstrString )
  {
    v15 = -2147024882;
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_6;
    LODWORD(v117) = 5441;
    v116 = (CUMRDPConnection *)"Failed to allocate SSL Info";
    v25 = (__int16 *)&dword_18019447C;
    psz = "SendPolicyData";
    v119 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
    v120 = (unsigned __int64)"Error HResult failed";
    p_psz = &v116;
    v113 = &psz;
    v112 = (unsigned __int64 *)&v119;
    v26 = &v120;
    goto LABEL_13;
  }
  v38 = v121;
  if ( *((_QWORD *)v121 + 25) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v136, v37, v22);
    v4 = *((_QWORD *)v121 + 25);
    v136 = v4;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v136);
    v38 = v121;
  }
  if ( *((_QWORD *)v38 + 66) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v144, v37, v22);
    v38 = v121;
    v3 = *((_QWORD *)v121 + 66);
    v144 = v3;
    if ( v3 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
      v38 = v121;
    }
  }
  if ( *((_QWORD *)v38 + 17) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v135, v37, v22);
    v5 = *((_QWORD *)v121 + 17);
    v135 = v5;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v135);
    v38 = v121;
  }
  if ( *((_QWORD *)v38 + 27) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v134, v37, v22);
    v6 = *((_QWORD *)v121 + 27);
    v134 = v6;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v134);
    v38 = v121;
  }
  v117 = (struct _WTS_POLICY_DATA *)*((_QWORD *)v38 + 28);
  if ( *((_QWORD *)v38 + 29) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v138, v37, v22);
    v2 = *((_QWORD *)v121 + 29);
    v138 = v2;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v138);
    v38 = v121;
  }
  if ( *((_QWORD *)v38 + 24) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v140, v37, v22);
    v7 = *((_QWORD *)v121 + 24);
    v140 = v7;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v140);
    v38 = v121;
  }
  if ( *((_QWORD *)v38 + 13) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v139, v37, v22);
    v9 = *((_QWORD *)v121 + 13);
    v139 = v9;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v139);
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v123);
  if ( !v4 || !v5 || !v6 && !v117 && !v2 || !v9 )
  {
    v15 = -2147019873;
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_7;
    v41 = "Connection is not initialized!";
    LODWORD(v117) = 5457;
    v42 = (__int16 *)byte_18019442B;
    goto LABEL_48;
  }
  v15 = (*(__int64 (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)v4 + 32LL))(v4, v160, 32);
  if ( v15 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_7;
    v41 = "m_spListener->GetListenerName";
    LODWORD(v117) = 5461;
    v42 = word_1801943DA;
LABEL_48:
    v116 = (CUMRDPConnection *)v41;
    psz = "SendPolicyData";
    v119 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
    v120 = (unsigned __int64)"Error HResult failed";
    v115 = v15;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v39,
      (_DWORD)v42,
      v17,
      v40,
      (__int64)&v120,
      (__int64)&v115,
      (__int64)&v119,
      (__int64)&v117,
      (__int64)&psz,
      (__int64)&v116);
    goto LABEL_7;
  }
  v157 = v3;
  v154 = v160;
  v156 = L"Local\\TS Certificate Update Event";
  if ( !(unsigned int)Containers::IsContainerModeEnabled()
    || (unsigned int)_o__wcsicmp(v160, L"31C5CE94259D4006A9E4")
    && (unsigned int)_o__wcsicmp(v160, L"41C5CE94259D4006A9E4") )
  {
    v18 = v121;
  }
  else
  {
    if ( (unsigned int)dword_1801B76C8 > 4 )
    {
      v116 = (CUMRDPConnection *)"In container, set m_fAlwaysEncryptCsData = FALSE";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v43,
        (unsigned int)byte_1801943B5,
        v44,
        v45,
        (__int64)&v116);
    }
    v18 = v121;
    *((_DWORD *)v121 + 184) = 0;
  }
  memset(&v146, 0, sizeof(v146));
  VariantInit(&v146);
  v146.vt = 11;
  v46 = -1;
  if ( !*((_DWORD *)v18 + 189) )
    v46 = 0;
  v47 = *((_QWORD *)v18 + 71);
  v146.iVal = v46;
  v15 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)v47 + 56LL))(
          v47,
          L"EnableWddmIdd",
          &v146);
  if ( v15 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
    {
LABEL_63:
      v19 = (CUMRDPConnection *)((char *)v18 + 64);
      goto LABEL_64;
    }
    LODWORD(v117) = 5492;
    v50 = (char *)&dword_180194364;
    goto LABEL_61;
  }
  v15 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)v18 + 12) + 56LL))(
          *((_QWORD *)v18 + 12),
          L"EnableWddmIdd",
          &v146);
  if ( v15 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_63;
    LODWORD(v117) = 5495;
    v50 = byte_180194313;
LABEL_61:
    v116 = (CUMRDPConnection *)"Failed to set CONN_PROPERTY_ENABLE_WDDM_IDD property";
    psz = "SendPolicyData";
LABEL_62:
    v115 = v15;
    v119 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
    v120 = (unsigned __int64)"Error HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v48,
      (_DWORD)v50,
      v17,
      v49,
      (__int64)&v120,
      (__int64)&v115,
      (__int64)&v119,
      (__int64)&v117,
      (__int64)&psz,
      (__int64)&v116);
    goto LABEL_63;
  }
  if ( v6 )
  {
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v6 + 96LL))(v6, *((unsigned int *)v18 + 158));
    v92 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 80LL))(v6);
    if ( v92 )
    {
      TCntPtr<IRdpSQMLogger>::SafeRelease(&v143, v90, v91);
      v93 = *(_QWORD *)v92;
      v143 = v92;
      (*(void (__fastcall **)(__int64))(v93 + 8))(v92);
      v94 = 0;
      v116 = (CUMRDPConnection *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v92 + 48LL))(v92);
      v95 = StringCchLengthW((const unsigned __int16 *)v116, 0x402u, &v120);
      if ( v96 )
      {
        if ( v95 >= 0 )
        {
          v97 = v120 + 1;
          v98 = (unsigned __int16 *)operator new[](saturated_mul(v120 + 1, 2u));
          v94 = v98;
          if ( v98 )
          {
            if ( (int)StringCchCopyW(v98, v97, (const unsigned __int16 *)v116) < 0 )
            {
              operator delete(v94);
              v94 = 0;
            }
          }
        }
      }
      Block = v94;
    }
    v15 = (*(__int64 (__fastcall **)(__int64, __int64, _BYTE **, __int64 *))(*(_QWORD *)v5 + 40LL))(
            v5,
            v6,
            &v154,
            &v125);
    if ( v15 < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_63;
      LODWORD(v117) = 5532;
      v116 = (CUMRDPConnection *)"Failed to create the stream object from endpoint";
      psz = "SendPolicyData";
      v50 = (char *)word_1801942C2;
      goto LABEL_62;
    }
  }
  else if ( v117 )
  {
    v15 = (*(__int64 (__fastcall **)(__int64, struct _WTS_POLICY_DATA *, _BYTE **, __int64 *))(*(_QWORD *)v5 + 48LL))(
            v5,
            v117,
            &v154,
            &v125);
    if ( v15 < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_63;
      LODWORD(v117) = 5539;
      v116 = (CUMRDPConnection *)"Failed to create the stream object from pipe";
      psz = "SendPolicyData";
      v50 = byte_180194271;
      goto LABEL_62;
    }
  }
  else if ( v2 )
  {
    v15 = (*(__int64 (__fastcall **)(__int64, __int64, _BYTE **, __int64 *))(*(_QWORD *)v5 + 72LL))(
            v5,
            v2,
            &v154,
            &v125);
    if ( v15 < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_63;
      LODWORD(v117) = 5549;
      v116 = (CUMRDPConnection *)"Failed to create the stream object from base stream";
      psz = "SendPolicyData";
      v50 = (char *)qword_180194220;
      goto LABEL_62;
    }
  }
  else if ( (unsigned int)dword_1801B76C8 > 2 )
  {
    psz = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
    v119 = "No transport to create a stream from!";
    v116 = (CUMRDPConnection *)"SendPolicyData";
    LODWORD(v117) = 5552;
    v115 = -2147418113;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (unsigned int)"SendPolicyData",
      (unsigned int)&byte_1801941D7,
      v17,
      v49,
      (__int64)&v119,
      (__int64)&v115,
      (__int64)&psz,
      (__int64)&v117,
      (__int64)&v116);
  }
  v15 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64, __int64 *, __int64))(*(_QWORD *)v9 + 24LL))(
          v9,
          &CLSID_RDPCoreConnection,
          v125,
          &v124,
          (__int64)v18 + 632);
  if ( v15 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_63;
    LODWORD(v117) = 5568;
    v116 = (CUMRDPConnection *)"Failed to create an rdp core connection";
    psz = "SendPolicyData";
    v50 = (char *)&word_180194186;
    goto LABEL_62;
  }
  v15 = (*(__int64 (__fastcall **)(__int64, struct IRDPCollection **))(*(_QWORD *)v124 + 80LL))(v124, &v122);
  if ( v15 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_63;
    LODWORD(v117) = 5571;
    v116 = (CUMRDPConnection *)"Failed to get core connection properties";
    psz = "SendPolicyData";
    v50 = byte_180194135;
    goto LABEL_62;
  }
  ATL::CComBSTR::CopyTo((ATL::CComBSTR *)&bstrString, &v152);
  ATL::CComBSTR::CopyTo((CUMRDPConnection *)((char *)v18 + 536), &v153);
  v149.vt = 11;
  v149.iVal = -1;
  v15 = (*(__int64 (__fastcall **)(struct IRDPCollection *, const wchar_t *, VARIANTARG *))(*(_QWORD *)v122 + 56LL))(
          v122,
          L"StackConfig",
          &pvarg);
  if ( v15 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_63;
    LODWORD(v117) = 5587;
    v116 = (CUMRDPConnection *)"Failed to set the property stack config";
    psz = "SendPolicyData";
    v50 = (char *)&dword_1801940E4;
    goto LABEL_62;
  }
  v15 = (*(__int64 (__fastcall **)(struct IRDPCollection *, const wchar_t *, VARIANTARG *))(*(_QWORD *)v122 + 56LL))(
          v122,
          L"SecurityConfig",
          &v152);
  if ( v15 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_63;
    LODWORD(v117) = 5590;
    v116 = (CUMRDPConnection *)"Failed to set the property security config";
    psz = "SendPolicyData";
    v50 = byte_180194093;
    goto LABEL_62;
  }
  v15 = (*(__int64 (__fastcall **)(struct IRDPCollection *, const wchar_t *, VARIANTARG *))(*(_QWORD *)v122 + 56LL))(
          v122,
          L"MonitorConfig",
          &v153);
  if ( v15 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_63;
    LODWORD(v117) = 5593;
    v116 = (CUMRDPConnection *)"Failed to set the property monitor config";
    psz = "SendPolicyData";
    v50 = (char *)word_180194042;
    goto LABEL_62;
  }
  v15 = (*(__int64 (__fastcall **)(struct IRDPCollection *, const wchar_t *, VARIANTARG *))(*(_QWORD *)v122 + 56LL))(
          v122,
          L"ShowProtocolHeaders",
          &v149);
  if ( v15 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_63;
    LODWORD(v117) = 5596;
    v116 = (CUMRDPConnection *)"Failed to set the show protocol headers config";
    psz = "SendPolicyData";
    v50 = byte_180193FF1;
    goto LABEL_62;
  }
  if ( v7 )
  {
    v147.llVal = v7;
    v147.vt = 13;
    (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)v7 + 8LL))(v7);
    v15 = (*(__int64 (__fastcall **)(struct IRDPCollection *, const wchar_t *, VARIANTARG *))(*(_QWORD *)v122 + 56LL))(
            v122,
            L"MultiTransportListener",
            &v147);
    if ( v15 < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_63;
      LODWORD(v117) = 5608;
      v116 = (CUMRDPConnection *)"Failed to set MultiTransport listener object";
      psz = "SendPolicyData";
      v50 = (char *)qword_180193FA0;
      goto LABEL_62;
    }
    if ( *((_QWORD *)v18 + 73) && *((_QWORD *)v18 + 12) )
    {
      if ( (unsigned int)dword_1801B76C8 > 4 )
      {
        v116 = (CUMRDPConnection *)"Adding m_spICETransportContext to spCollection";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v48,
          (unsigned int)byte_180193F7B,
          v17,
          v49,
          (__int64)&v116);
      }
      v99 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v18 + 12))(
              *((_QWORD *)v18 + 12),
              &IID_IRDPCollection,
              &v142);
      if ( v99 < 0 && (unsigned int)dword_1801B76C8 > 3 )
      {
        LODWORD(v117) = v99;
        v116 = (CUMRDPConnection *)"SendPolicyData";
        psz = "Failed to m_spPlatformContext->QueryInterface IID_IRDPCollection";
        v119 = "HResult failed but continue";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          dword_1801B76C8,
          (unsigned int)&dword_180193F3C,
          v100,
          v101,
          (__int64)&v119,
          (__int64)&psz,
          (__int64)&v117,
          (__int64)&v116);
      }
      v102 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD))(*(_QWORD *)v142 + 80LL))(
               v142,
               L"ICETransport",
               *((_QWORD *)v18 + 73));
      if ( v102 < 0 && (unsigned int)dword_1801B76C8 > 3 )
      {
        LODWORD(v117) = v102;
        v116 = (CUMRDPConnection *)"SendPolicyData";
        psz = "Failed to add m_spICETransportContext to spPlatformProperties";
        v119 = "HResult failed but continue";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          dword_1801B76C8,
          (unsigned int)byte_180193EFD,
          v103,
          v104,
          (__int64)&v119,
          (__int64)&psz,
          (__int64)&v117,
          (__int64)&v116);
      }
    }
  }
  if ( v155 )
  {
    v151.vt = 11;
    v151.iVal = -1;
    v15 = (*(__int64 (__fastcall **)(struct IRDPCollection *, const wchar_t *, VARIANTARG *))(*(_QWORD *)v122 + 56LL))(
            v122,
            L"RDPENCSTACK_ENCRYPTED_STREAM",
            &v151);
    if ( v15 < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_63;
      psz = "SendPolicyData";
      v116 = (CUMRDPConnection *)"Failed to set the Encrypted Stream property";
      v50 = (char *)&dword_180193EAC;
      LODWORD(v117) = 5629;
      goto LABEL_62;
    }
  }
  v15 = CUMRDPConnection::SetExtendedUMRDPStackInfo((CUMRDPConnection *)((char *)v18 - 88), v122);
  if ( v15 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_63;
    psz = "SendPolicyData";
    v116 = (CUMRDPConnection *)"Failed to set UMRDP stack configuration info!";
    v50 = byte_180193E5B;
    LODWORD(v117) = 5642;
    goto LABEL_62;
  }
  v105 = *((_QWORD *)v18 + 12);
  if ( v105 )
  {
    if ( (*(int (__fastcall **)(__int64, const wchar_t *, unsigned int *))(*(_QWORD *)v105 + 40LL))(
           v105,
           L"WVD::ConnectionControlEnabledFeatures",
           &v126) >= 0 )
    {
      v15 = (*(__int64 (__fastcall **)(struct IRDPCollection *, const wchar_t *, _QWORD))(*(_QWORD *)v122 + 72LL))(
              v122,
              L"WVD::ConnectionControlEnabledFeatures",
              v126);
      if ( v15 < 0 )
      {
        if ( (unsigned int)dword_1801B76C8 <= 2 )
          goto LABEL_63;
        psz = "SendPolicyData";
        v116 = (CUMRDPConnection *)"Failed to set conctrl features property";
        v50 = (char *)word_180193E0A;
        LODWORD(v117) = 5651;
        goto LABEL_62;
      }
    }
  }
  v106 = *((_QWORD *)v18 + 12);
  if ( v106 )
  {
    if ( (*(int (__fastcall **)(__int64, const wchar_t *, unsigned int *))(*(_QWORD *)v106 + 32LL))(
           v106,
           L"EnableAuthOverConnectionControl",
           &v127) >= 0 )
    {
      v15 = (*(__int64 (__fastcall **)(struct IRDPCollection *, const wchar_t *, _QWORD))(*(_QWORD *)v122 + 64LL))(
              v122,
              L"EnableAuthOverConnectionControl",
              v127);
      if ( v15 < 0 )
      {
        if ( (unsigned int)dword_1801B76C8 <= 2 )
          goto LABEL_63;
        psz = "SendPolicyData";
        v116 = (CUMRDPConnection *)"Failed to set auth over conctrl property";
        v50 = byte_180193DB9;
        LODWORD(v117) = 5661;
        goto LABEL_62;
      }
    }
  }
  v107 = *((_QWORD *)v18 + 12);
  if ( v107 )
  {
    if ( (*(int (__fastcall **)(__int64, const wchar_t *, unsigned int *))(*(_QWORD *)v107 + 32LL))(
           v107,
           L"EnableFakeVCMgr",
           &v128) >= 0 )
    {
      v15 = (*(__int64 (__fastcall **)(struct IRDPCollection *, const wchar_t *, _QWORD))(*(_QWORD *)v122 + 64LL))(
              v122,
              L"EnableFakeVCMgr",
              v128);
      if ( v15 < 0 )
      {
        if ( (unsigned int)dword_1801B76C8 <= 2 )
          goto LABEL_63;
        psz = "SendPolicyData";
        v116 = (CUMRDPConnection *)"Failed to set enable fake VC mgr property";
        v50 = (char *)qword_180193D68;
        LODWORD(v117) = 5671;
        goto LABEL_62;
      }
    }
  }
  v108 = __RDPAPIDLL__CreateInstance(
           *((struct IUnknown **)v18 + 12),
           &CLSID_IRDLicenseServer,
           &IID_IRDLicenseServer,
           &v130);
  if ( v108 < 0 && (unsigned int)dword_1801B76C8 > 3 )
  {
    LODWORD(v117) = v108;
    v116 = (CUMRDPConnection *)"SendPolicyData";
    psz = "Failed to create the interface with the License Server";
    v119 = "HResult failed but continue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      dword_1801B76C8,
      (unsigned int)byte_180193D29,
      v109,
      v110,
      (__int64)&v119,
      (__int64)&psz,
      (__int64)&v117,
      (__int64)&v116);
  }
  if ( v130 )
  {
    v15 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v130 + 24LL))(v130);
    if ( v15 < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_63;
      psz = "SendPolicyData";
      v116 = (CUMRDPConnection *)"Failed to initialize the interface with the License Server";
      v50 = (char *)qword_180193CD8;
      LODWORD(v117) = 5682;
      goto LABEL_62;
    }
  }
  v15 = (*(__int64 (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v124 + 40LL))(
          v124,
          ((unsigned __int64)v18 - 8) & -(__int64)(v18 != (CUMRDPConnection *)88));
  if ( v15 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_63;
    psz = "SendPolicyData";
    v116 = (CUMRDPConnection *)"Failed to Start Connection on RDPCore Connection object";
    v50 = &byte_180193C87;
    LODWORD(v117) = 5687;
    goto LABEL_62;
  }
  v15 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v124 + 88LL))(
          v124,
          &v145);
  if ( v15 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_63;
    psz = "SendPolicyData";
    v116 = (CUMRDPConnection *)"Failed to get stack";
    v50 = (char *)&word_180193C36;
    LODWORD(v117) = 5690;
    goto LABEL_62;
  }
  v15 = (**v145)(v145, &IID_IRDPWDUMX_StackEx, &v133);
  if ( v15 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_63;
    psz = "SendPolicyData";
    v116 = (CUMRDPConnection *)"Failed to QI for RdpStack from Unknown";
    v50 = byte_180193BE5;
    LODWORD(v117) = 5693;
    goto LABEL_62;
  }
  v15 = (*(__int64 (__fastcall **)(struct IRDPCollection *, const wchar_t *, GUID *, __int64 *))(*(_QWORD *)v122 + 48LL))(
          v122,
          L"UMTSInputPlugin",
          &IID_IUMTSInputMgr,
          &v132);
  if ( v15 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_63;
    psz = "SendPolicyData";
    v116 = (CUMRDPConnection *)"Failed to get input plugin property form core connection";
    v50 = (char *)&dword_180193B94;
    LODWORD(v117) = 5700;
    goto LABEL_62;
  }
  v15 = (*(__int64 (__fastcall **)(struct IRDPCollection *, const wchar_t *, GUID *, __int64 *))(*(_QWORD *)v122 + 48LL))(
          v122,
          L"UMTSCommandPlugin",
          &IID_IUMTSCommandMgr,
          &v131);
  if ( v15 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_63;
    psz = "SendPolicyData";
    v116 = (CUMRDPConnection *)"Failed to get command plugin property form core connection";
    v50 = byte_180193B43;
    LODWORD(v117) = 5706;
    goto LABEL_62;
  }
  v15 = (*(__int64 (__fastcall **)(struct IRDPCollection *, const wchar_t *, GUID *, __int64 *))(*(_QWORD *)v122 + 48LL))(
          v122,
          L"UMTSLICPlugin",
          &IID_IWRdsProtocolLicenseConnection,
          &v141);
  if ( v15 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_63;
    psz = "SendPolicyData";
    v116 = (CUMRDPConnection *)"Failed to get Licesing plugin property form core connection";
    v50 = (char *)word_180193AF2;
    LODWORD(v117) = 5712;
    goto LABEL_62;
  }
  v19 = (CUMRDPConnection *)((char *)v18 + 64);
  v14 = *((_DWORD *)v18 + 18) == 0;
  v120 = (unsigned __int64)v18 + 64;
  if ( !v14 )
    PAL_System_CritSecEnter(*(_QWORD *)v19, v16, v17);
  if ( v124 != *((_QWORD *)v18 + 14) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease((char *)v18 + 112, v16, v17);
    *((_QWORD *)v18 + 14) = v124;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)v18 + 112);
  }
  if ( v125 != *((_QWORD *)v18 + 15) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease((char *)v18 + 120, v16, v17);
    *((_QWORD *)v18 + 15) = v125;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)v18 + 120);
  }
  if ( v122 != *((struct IRDPCollection **)v18 + 16) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease((char *)v18 + 128, v16, v17);
    *((_QWORD *)v18 + 16) = v122;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)v18 + 128);
  }
  if ( v133 != *((_QWORD *)v18 + 18) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease((char *)v18 + 144, v16, v17);
    *((_QWORD *)v18 + 18) = v133;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)v18 + 144);
  }
  if ( v132 != *((_QWORD *)v18 + 20) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease((char *)v18 + 160, v16, v17);
    v111 = v132;
    *((_QWORD *)v18 + 20) = v132;
    if ( v111 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v111 + 8LL))(v111);
  }
  if ( v131 != *((_QWORD *)v18 + 21) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease((char *)v18 + 168, v16, v17);
    *((_QWORD *)v18 + 21) = v131;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)v18 + 168);
  }
  if ( v141 != *((_QWORD *)v18 + 23) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease((char *)v18 + 184, v16, v17);
    *((_QWORD *)v18 + 23) = v141;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)v18 + 184);
  }
  v14 = *((_DWORD *)v18 + 160) == 0;
  *((_QWORD *)v18 + 28) = 0;
  if ( v14 )
  {
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v120);
    goto LABEL_70;
  }
  v15 = -2147467260;
  if ( (unsigned int)dword_1801B76C8 > 2 )
  {
    v116 = (CUMRDPConnection *)"SendPolicyData";
    psz = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
    LODWORD(v117) = 5735;
    v119 = "Connection was terminated while sending policy data";
    v115 = -2147467260;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      -2147467260,
      (unsigned int)byte_180193AA9,
      v17,
      v49,
      (__int64)&v119,
      (__int64)&v115,
      (__int64)&psz,
      (__int64)&v117,
      (__int64)&v116);
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v120);
LABEL_64:
  v14 = *((_DWORD *)v19 + 2) == 0;
  v116 = v19;
  if ( !v14 )
    PAL_System_CritSecEnter(*(_QWORD *)v19, v16, v17);
  if ( v124 && !*((_QWORD *)v18 + 14) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease((char *)v18 + 112, v16, v17);
    *((_QWORD *)v18 + 14) = v124;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)v18 + 112);
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v116);
  CUMRDPConnection::TerminateInstance((CUMRDPConnection *)((char *)v18 - 40));
LABEL_70:
  v51 = Block;
  if ( Block )
  {
    Block = 0;
    operator delete(v51);
  }
  VariantClear(&pvarg);
  VariantClear(&v152);
  VariantClear(&v153);
  VariantClear(&v149);
  VariantClear(&v147);
  EventActivityIdControl(2u, &ActivityId);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v142, v52, v53);
  v56 = v130;
  if ( v130 )
  {
    v130 = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v56 + 16LL))(v56);
  }
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v143, v54, v55);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v138, v57, v58);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v139, v59, v60);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v140, v61, v62);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v150, v63, v64);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v141, v65, v66);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v131, v67, v68);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v132, v69, v70);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v133, v71, v72);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v122, v73, v74);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v124, v75, v76);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v134, v77, v78);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v135, v79, v80);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v144, v81, v82);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v136, v83, v84);
  SysFreeString(bstrString);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v145, v85, v86);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v125, v87, v88);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1800527c0  push    rbp
0x1800527c2  push    rbx
0x1800527c3  push    rsi
0x1800527c4  push    rdi
0x1800527c5  push    r12
0x1800527c7  push    r13
0x1800527c9  push    r14
0x1800527cb  push    r15
0x1800527cd  lea     rbp, [rsp-1B8h]
0x1800527d5  sub     rsp, 2B8h
0x1800527dc  mov     rax, cs:__security_cookie
0x1800527e3  xor     rax, rsp
0x1800527e6  mov     [rbp+1F0h+var_50], rax
0x1800527ed  xor     eax, eax
0x1800527ef  mov     [rbp+1F0h+var_270], rcx
0x1800527f3  xor     r15d, r15d
0x1800527f6  mov     qword ptr [rbp+1F0h+pvarg+10h], rax
0x1800527fa  xorps   xmm0, xmm0
0x1800527fd  mov     [rbp+1F0h+var_250], r15
0x180052801  xorps   xmm1, xmm1
0x180052804  mov     [rbp+1F0h+var_1C0], r15
0x180052808  lea     rcx, [rbp+1F0h+pvarg]; pvarg
0x18005280c  mov     qword ptr [rbp+1F0h+var_138+10h], rax
0x180052813  movups  xmmword ptr [rbp+1F0h+pvarg], xmm0
0x180052817  mov     qword ptr [rbp+1F0h+var_120+10h], rax
0x18005281e  movups  xmmword ptr [rbp+1F0h+var_138], xmm1
0x180052825  mov     qword ptr [rbp+1F0h+var_170+10h], rax
0x18005282c  movups  xmmword ptr [rbp+1F0h+var_120], xmm0
0x180052833  mov     qword ptr [rbp+1F0h+var_1A0+10h], rax
0x180052837  movups  xmmword ptr [rbp+1F0h+var_170], xmm1
0x18005283e  mov     qword ptr [rbp+1F0h+var_150+10h], rax
0x180052845  movups  xmmword ptr [rbp+1F0h+var_1A0], xmm0
0x180052849  mov     [rbp+1F0h+var_248], r15d
0x18005284d  movups  xmmword ptr [rbp+1F0h+var_150], xmm1
0x180052854  mov     [rbp+1F0h+var_23C], r15d
0x180052858  mov     [rbp+1F0h+var_244], r15d
0x18005285c  mov     [rbp+1F0h+var_240], r15d
0x180052860  mov     [rsp+2F0h+var_290], rdx
0x180052865  call    cs:__imp_VariantInit
0x18005286b  lea     rcx, [rbp+1F0h+var_138]; pvarg
0x180052872  call    cs:__imp_VariantInit
0x180052878  lea     rcx, [rbp+1F0h+var_120]; pvarg
0x18005287f  call    cs:__imp_VariantInit
0x180052885  lea     rcx, [rbp+1F0h+var_170]; pvarg
0x18005288c  call    cs:__imp_VariantInit
0x180052892  lea     rcx, [rbp+1F0h+var_1A0]; pvarg
0x180052896  call    cs:__imp_VariantInit
0x18005289c  lea     rcx, [rbp+1F0h+var_150]; pvarg
0x1800528a3  call    cs:__imp_VariantInit
0x1800528a9  xor     edx, edx; Val
0x1800528ab  mov     [rbp+1F0h+bstrString], r15
0x1800528af  lea     r8d, [r15+60h]; Size
0x1800528b3  lea     rcx, [rbp+1F0h+var_100]; void *
0x1800528ba  call    memset_0
0x1800528bf  xor     eax, eax
0x1800528c1  mov     [rsp+2F0h+var_278], r15
0x1800528c6  mov     [rbp+1F0h+var_1D0], rax
0x1800528ca  lea     rdx, [rbp+1F0h+ActivityId]; ActivityId
0x1800528d1  mov     [rbp+1F0h+var_238], rax
0x1800528d5  lea     ecx, [r15+4]; ControlCode
0x1800528d9  mov     [rbp+1F0h+var_1D8], rax
0x1800528dd  mov     ebx, r15d
0x1800528e0  mov     rax, [rbp+1F0h+var_270]
0x1800528e4  mov     r14d, r15d
0x1800528e7  mov     [rbp+1F0h+var_208], r15
0x1800528eb  mov     esi, r15d
0x1800528ee  mov     [rbp+1F0h+var_1C8], rbx
0x1800528f2  mov     edi, r15d
0x1800528f5  mov     [rbp+1F0h+var_210], r15
0x1800528f9  mov     r13d, r15d
0x1800528fc  movups  xmm0, xmmword ptr [rax+2D0h]
0x180052903  mov     [rbp+1F0h+var_218], r15
0x180052907  mov     r12d, r15d
0x18005290a  mov     [rbp+1F0h+var_258], r15
0x18005290e  movdqu  xmmword ptr [rbp+1F0h+ActivityId.Data1], xmm0
0x180052916  mov     [rbp+1F0h+var_268], r15
0x18005291a  mov     [rbp+1F0h+var_220], r15
0x18005291e  mov     [rbp+1F0h+var_228], r15
0x180052922  mov     [rbp+1F0h+var_230], r15
0x180052926  mov     [rbp+1F0h+var_1E0], r15
0x18005292a  mov     [rbp+1F0h+var_158], r15
0x180052931  mov     [rbp+1F0h+var_1E8], r15
0x180052935  mov     [rbp+1F0h+var_1F0], r15
0x180052939  mov     [rbp+1F0h+var_1F8], r15
0x18005293d  call    cs:__imp_EventActivityIdControl
0x180052943  mov     rax, [rbp+1F0h+var_270]
0x180052947  lea     rcx, [rax+40h]
0x18005294b  mov     [rbp+1F0h+var_260], rcx
0x18005294f  cmp     [rcx+8], ebx
0x180052952  jz      short loc_180052961
0x180052954  mov     rcx, [rcx]
0x180052957  call    cs:__imp_PAL_System_CritSecEnter
0x18005295d  mov     rax, [rbp+1F0h+var_270]
0x180052961  lea     rcx, [rax-58h]
0x180052965  test    byte ptr [rcx+1Ch], 4
0x180052969  mov     [rsp+2F0h+var_298], rcx
0x18005296e  jz      loc_180052A0B
0x180052974  mov     eax, cs:dword_1801B76C8
0x18005297a  mov     ecx, 80004004h
0x18005297f  mov     r14d, ecx
0x180052982  cmp     eax, 2
0x180052985  jbe     short loc_1800529F5
0x180052987  lea     rax, aSendpolicydata; "SendPolicyData"
0x18005298e  mov     [rsp+2F0h+var_2A0], 1517h
0x180052996  mov     [rsp+2F0h+var_278], rax
0x18005299b  lea     rdx, byte_18019456F
0x1800529a2  lea     rax, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x1800529a9  mov     dword ptr [rsp+2F0h+var_290], ecx
0x1800529ad  mov     [rsp+2F0h+var_280], rax
0x1800529b2  lea     rax, aSendpolicydata_0; "SendPolicyData quitting because object "...
0x1800529b9  mov     [rsp+2F0h+psz], rax
0x1800529be  lea     rax, [rsp+2F0h+var_278]
0x1800529c3  mov     [rsp+2F0h+var_2B0], rax
0x1800529c8  lea     rax, [rsp+2F0h+var_2A0]
0x1800529cd  mov     [rsp+2F0h+var_2B8], rax
0x1800529d2  lea     rax, [rsp+2F0h+var_280]
0x1800529d7  mov     [rsp+2F0h+var_2C0], rax
0x1800529dc  lea     rax, [rsp+2F0h+var_290]
0x1800529e1  mov     [rsp+2F0h+var_2C8], rax
0x1800529e6  lea     rax, [rsp+2F0h+psz]
0x1800529eb  mov     [rsp+2F0h+var_2D0], rax
0x1800529f0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800529f5  lea     rcx, [rbp+1F0h+var_260]; this
0x1800529f9  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x1800529fe  mov     rbx, [rbp+1F0h+var_270]
0x180052a02  mov     r15, [rbp+1F0h+var_260]
0x180052a06  jmp     loc_1800530C8
0x180052a0b  mov     rcx, [rax+228h]
0x180052a12  test    rcx, rcx
0x180052a15  jz      short loc_180052A2A
0x180052a17  mov     rax, [rcx]
0x180052a1a  lea     rdx, aSendpolicydata_1; "SendPolicyData"
0x180052a21  mov     rax, [rax+50h]
0x180052a25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052a2a  mov     edx, 8; len
0x180052a2f  xor     ecx, ecx; psz
0x180052a31  call    cs:__imp_SysAllocStringByteLen
0x180052a37  mov     qword ptr [rbp+1F0h+pvarg+8], rax
0x180052a3b  mov     rdx, rax
0x180052a3e  test    rax, rax
0x180052a41  jnz     loc_180052AE3
0x180052a47  mov     eax, cs:dword_1801B76C8
0x180052a4d  mov     ecx, 8007000Eh
0x180052a52  mov     r14d, ecx
0x180052a55  cmp     eax, 2
0x180052a58  jbe     short loc_1800529F5
0x180052a5a  lea     rax, aFailedToAlloca_2; "Failed to allocate Monitor Config"
0x180052a61  mov     dword ptr [rsp+2F0h+var_290], 1523h
0x180052a69  mov     [rsp+2F0h+psz], rax
0x180052a6e  lea     rdx, word_18019451E
0x180052a75  lea     rax, aSendpolicydata; "SendPolicyData"
0x180052a7c  mov     [rsp+2F0h+var_280], rax
0x180052a81  lea     rax, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x180052a88  mov     [rsp+2F0h+var_278], rax
0x180052a8d  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180052a94  mov     [rsp+2F0h+var_298], rax
0x180052a99  lea     rax, [rsp+2F0h+psz]
0x180052a9e  mov     [rsp+2F0h+var_2A8], rax
0x180052aa3  lea     rax, [rsp+2F0h+var_280]
0x180052aa8  mov     [rsp+2F0h+var_2B0], rax
0x180052aad  lea     rax, [rsp+2F0h+var_290]
0x180052ab2  mov     [rsp+2F0h+var_2B8], rax
0x180052ab7  lea     rax, [rsp+2F0h+var_278]
0x180052abc  mov     [rsp+2F0h+var_2C0], rax
0x180052ac1  lea     rax, [rsp+2F0h+var_2A0]
0x180052ac6  mov     [rsp+2F0h+var_2C8], rax
0x180052acb  lea     rax, [rsp+2F0h+var_298]
0x180052ad0  mov     [rsp+2F0h+var_2A0], ecx
0x180052ad4  mov     [rsp+2F0h+var_2D0], rax
0x180052ad9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180052ade  jmp     loc_1800529F5
0x180052ae3  mov     r8, [rsp+2F0h+var_290]
0x180052ae8  mov     eax, 8
0x180052aed  mov     word ptr [rbp+1F0h+pvarg], ax
0x180052af1  movzx   ecx, byte ptr [r8]
0x180052af5  shl     ecx, 3
0x180052af8  xor     ecx, [rdx]
0x180052afa  and     ecx, eax
0x180052afc  xor     ecx, [rdx]
0x180052afe  mov     [rdx], ecx
0x180052b00  movzx   eax, byte ptr [r8+1]
0x180052b05  shl     eax, 7
0x180052b08  xor     eax, ecx
0x180052b0a  and     eax, 80h
0x180052b0f  xor     eax, ecx
0x180052b11  mov     [rdx], eax
0x180052b13  mov     ecx, eax
0x180052b15  xor     ecx, [r8+4]
0x180052b19  and     ecx, 7
0x180052b1c  xor     ecx, eax
0x180052b1e  mov     [rdx], ecx
0x180052b20  movzx   eax, byte ptr [r8+8]
0x180052b25  lea     r8, [rbp+1F0h+var_23C]
0x180052b29  shl     eax, 4
0x180052b2c  xor     eax, ecx
0x180052b2e  and     eax, 70h
0x180052b31  xor     eax, ecx
0x180052b33  mov     [rdx], eax
0x180052b35  lea     rdx, aSkiplegacyrdp; "SkipLegacyRdp"
0x180052b3c  mov     rax, [rbp+1F0h+var_270]
0x180052b40  mov     rcx, [rax+60h]
0x180052b44  mov     rax, [rcx]
0x180052b47  mov     rax, [rax+20h]
0x180052b4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052b50  test    eax, eax
0x180052b52  mov     rax, [rbp+1F0h+var_270]
0x180052b56  js      short loc_180052B63
0x180052b58  cmp     [rbp+1F0h+var_23C], ebx
0x180052b5b  jz      short loc_180052B63
0x180052b5d  mov     [rax+20Ch], bl
0x180052b63  mov     rdx, [rsp+2F0h+var_290]
0x180052b68  lea     r9, [rbp+1F0h+var_100]; struct RDPENC_SECFILTER_SETTINGS *
0x180052b6f  mov     rcx, [rsp+2F0h+var_298]; this
0x180052b74  add     rax, 0F0h
0x180052b7a  mov     [rsp+2F0h+psz], rax
0x180052b7f  mov     r8b, [rdx+8]; unsigned __int8
0x180052b83  mov     rdx, rax; struct _SSLINFO *
0x180052b86  call    ?SSLInfoToSecFilterSettings@CUMRDPConnection@@IEAAJPEAU_SSLINFO@@EPEAURDPENC_SECFILTER_SETTINGS@@@Z; CUMRDPConnection::SSLInfoToSecFilterSettings(_SSLINFO *,uchar,RDPENC_SECFILTER_SETTINGS *)
0x180052b8b  mov     [rsp+2F0h+var_2A0], eax
0x180052b8f  test    eax, eax
0x180052b91  jns     loc_180052C33
0x180052b97  mov     ecx, cs:dword_1801B76C8
0x180052b9d  cmp     ecx, 2
0x180052ba0  jbe     loc_180052C2B
0x180052ba6  mov     r14d, [rsp+2F0h+var_2A0]
0x180052bab  lea     rax, aFailedToInitia_14; "Failed to initialize sec filter setting"...
0x180052bb2  mov     [rsp+2F0h+var_298], rax
0x180052bb7  lea     rdx, byte_1801944CD
0x180052bbe  lea     rax, aSendpolicydata; "SendPolicyData"
0x180052bc5  mov     dword ptr [rsp+2F0h+var_290], 153Ch
0x180052bcd  mov     [rsp+2F0h+psz], rax
0x180052bd2  lea     rax, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x180052bd9  mov     [rsp+2F0h+var_280], rax
0x180052bde  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180052be5  mov     [rsp+2F0h+var_278], rax
0x180052bea  lea     rax, [rsp+2F0h+var_298]
0x180052bef  mov     [rsp+2F0h+var_2A8], rax
0x180052bf4  lea     rax, [rsp+2F0h+psz]
0x180052bf9  mov     [rsp+2F0h+var_2B0], rax
0x180052bfe  lea     rax, [rsp+2F0h+var_290]
0x180052c03  mov     [rsp+2F0h+var_2B8], rax
0x180052c08  lea     rax, [rsp+2F0h+var_280]
0x180052c0d  mov     [rsp+2F0h+var_2C0], rax
0x180052c12  lea     rax, [rsp+2F0h+var_2A0]
0x180052c17  mov     [rsp+2F0h+var_2C8], rax
0x180052c1c  lea     rax, [rsp+2F0h+var_278]
0x180052c21  mov     [rsp+2F0h+var_2A0], r14d
0x180052c26  jmp     loc_180052AD4
0x180052c2b  mov     r14d, eax
0x180052c2e  jmp     loc_1800529F5
0x180052c33  mov     rcx, [rsp+2F0h+psz]; psz
0x180052c38  mov     edx, 120h; len
0x180052c3d  call    cs:__imp_SysAllocStringByteLen
0x180052c43  mov     rdx, rax; unsigned __int16 *
0x180052c46  lea     rcx, [rbp+1F0h+bstrString]; this
0x180052c4a  call    ?Attach@CComBSTR@ATL@@QEAAXPEAG@Z; ATL::CComBSTR::Attach(ushort *)
0x180052c4f  cmp     [rbp+1F0h+bstrString], rbx
0x180052c53  jnz     loc_180052CEB
0x180052c59  mov     eax, cs:dword_1801B76C8
0x180052c5f  mov     ecx, 8007000Eh
0x180052c64  mov     r14d, ecx
0x180052c67  cmp     eax, 2
0x180052c6a  jbe     loc_1800529F5
0x180052c70  lea     rax, aFailedToAlloca_4; "Failed to allocate SSL Info"
0x180052c77  mov     dword ptr [rsp+2F0h+var_290], 1541h
0x180052c7f  mov     [rsp+2F0h+var_298], rax
0x180052c84  lea     rdx, dword_18019447C
0x180052c8b  lea     rax, aSendpolicydata; "SendPolicyData"
0x180052c92  mov     [rsp+2F0h+psz], rax
0x180052c97  lea     rax, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x180052c9e  mov     [rsp+2F0h+var_280], rax
0x180052ca3  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180052caa  mov     [rsp+2F0h+var_278], rax
0x180052caf  lea     rax, [rsp+2F0h+var_298]
0x180052cb4  mov     [rsp+2F0h+var_2A8], rax
0x180052cb9  lea     rax, [rsp+2F0h+psz]
0x180052cbe  mov     [rsp+2F0h+var_2B0], rax
0x180052cc3  lea     rax, [rsp+2F0h+var_290]
0x180052cc8  mov     [rsp+2F0h+var_2B8], rax
0x180052ccd  lea     rax, [rsp+2F0h+var_280]
0x180052cd2  mov     [rsp+2F0h+var_2C0], rax
0x180052cd7  lea     rax, [rsp+2F0h+var_2A0]
0x180052cdc  mov     [rsp+2F0h+var_2C8], rax
0x180052ce1  lea     rax, [rsp+2F0h+var_278]
0x180052ce6  jmp     loc_180052AD0
0x180052ceb  mov     rax, [rbp+1F0h+var_270]
0x180052cef  cmp     [rax+0C8h], rbx
0x180052cf6  jz      short loc_180052D1D
0x180052cf8  lea     rcx, [rbp+1F0h+var_208]
0x180052cfc  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x180052d01  mov     rax, [rbp+1F0h+var_270]
0x180052d05  lea     rcx, [rbp+1F0h+var_208]
0x180052d09  mov     r14, [rax+0C8h]
0x180052d10  mov     [rbp+1F0h+var_208], r14
0x180052d14  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x180052d19  mov     rax, [rbp+1F0h+var_270]
0x180052d1d  cmp     [rax+210h], rbx
0x180052d24  jz      short loc_180052D56
0x180052d26  lea     rcx, [rbp+1F0h+var_1C8]
0x180052d2a  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
  ... truncated ...
```
