# AvcEncoder::InitializeInput(AvcEncoderFrameParam const &,QPSettings const &,AvcEncodeSettings::MftSetting &,ulong,ulong,int,int,ComPlainSmartPtr<CMFApi>,ID3D11ShaderResourceView *,IUnknown *)

- ea: `0x180089330`
- end: `0x18008a730`
- name: `?InitializeInput@AvcEncoder@@UEAAJAEBUAvcEncoderFrameParam@@AEBUQPSettings@@AEAW4MftSetting@AvcEncodeSettings@@KKHHV?$ComPlainSmartPtr@VCMFApi@@@@PEAUID3D11ShaderResourceView@@PEAUIUnknown@@@Z`
- size: `5120`
- prototype: `__int64 __usercall@<rax>(AvcEncoder *this@<rcx>, int, int, int, int, __int64, struct ID3D11ShaderResourceView *, __int64)`
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800015f0`
- `0x180002fcc`
- `0x180009628`
- `0x180013bf0`
- `0x18002e600`
- `0x18002f7f4`
- `0x180032f60`
- `0x180033958`
- `0x180033964`
- `0x180033da0`
- `0x1800348d4`
- `0x180034970`
- `0x180059838`
- `0x1800598d0`
- `0x180084ba0`
- `0x180086e8c`
- `0x180089330`
- `0x18008a738`
- `0x18008a890`
- `0x18008ca00`
- `0x1800dbf70`
- `0x1800e0fc0`
- `0x1800e3c50`
- `0x18014d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180089d40`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180089d5f`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180089d40`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180089d5f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18008995e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18008995e`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008963b`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180089708`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180089fb1`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008a14a`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008a190`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008a2e1`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008a330`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008a421`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008a498`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008a4de`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008a524`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008a567`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008963b`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180089708`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180089fb1`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008a14a`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008a190`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008a2e1`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008a330`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008a421`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008a498`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008a4de`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008a524`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008a567`
- `OLEAUT32!__imp_VariantInit` at `0x1800893ac`
- `OLEAUT32!__imp_VariantInit` at `0x1800893ac`
- `OLEAUT32!__imp_VariantClear` at `0x18008a6e2`
- `OLEAUT32!__imp_VariantClear` at `0x18008a6e2`

## string_xrefs

- `0x18008a657`: `No QP settings given to AVC codec, or QP outside of AVC spec range given.`
- `0x180089ace`: `create and initialize hardware encoder failed, and it is required`

## pseudocode

```c
__int64 __fastcall AvcEncoder::InitializeInput(
        AvcEncoder *this,
        __int64 a2,
        const char *a3,
        const char *a4,
        unsigned int a5,
        unsigned int a6,
        int a7,
        int a8,
        __int64 *a9,
        struct ID3D11ShaderResourceView *a10,
        const char *a11)
{
  struct ID3D11ShaderResourceView *v12; // rbx
  int v16; // r8d
  int v17; // r9d
  __int64 v18; // rcx
  unsigned __int8 v19; // al
  unsigned int v20; // ecx
  int v21; // edx
  int v22; // r8d
  unsigned int v23; // r8d
  unsigned int v24; // r9d
  int v25; // ebx
  __int64 OutputAvc; // rax
  unsigned int v27; // ecx
  unsigned __int64 v28; // rcx
  void *v29; // rax
  __int64 v30; // rcx
  int ActivityIdPrefix; // eax
  int v32; // edx
  const char *v33; // rcx
  size_t v34; // r8
  __int64 v35; // r13
  __int64 v36; // rcx
  int v37; // ebx
  unsigned int v38; // eax
  int v39; // ecx
  int v40; // r8d
  int v41; // r9d
  CMFApi *v42; // rcx
  int PreferredHwAdapterFromSRV; // eax
  unsigned int v44; // r13d
  unsigned __int16 *bstrVal; // rbx
  __int64 v46; // rcx
  int v47; // r8d
  int v48; // r9d
  int *v49; // rdx
  const char **v50; // rax
  const char *v51; // rcx
  char *v52; // r13
  int DefaultOrFallbackAvcEncoderInfo; // eax
  int v54; // r13d
  const wchar_t *v55; // rcx
  const char *v56; // rcx
  _QWORD *v57; // rbx
  struct _EVENT_DATA_DESCRIPTOR *v58; // rcx
  struct _EVENT_DATA_DESCRIPTOR *v59; // rax
  struct _EVENT_DATA_DESCRIPTOR v60; // xmm0
  struct _EVENT_DATA_DESCRIPTOR v61; // xmm1
  struct _EVENT_DATA_DESCRIPTOR v62; // xmm0
  struct _EVENT_DATA_DESCRIPTOR v63; // xmm1
  struct _EVENT_DATA_DESCRIPTOR v64; // xmm0
  struct _EVENT_DATA_DESCRIPTOR v65; // xmm1
  struct _EVENT_DATA_DESCRIPTOR v66; // xmm0
  struct _EVENT_DATA_DESCRIPTOR v67; // xmm1
  struct _EVENT_DATA_DESCRIPTOR v68; // xmm1
  struct _EVENT_DATA_DESCRIPTOR v69; // xmm0
  ULONGLONG Ptr; // rax
  _QWORD **v71; // rcx
  AvcSoftWareEncoder *v72; // r8
  int v73; // r13d
  int v74; // eax
  unsigned int v75; // xmm0_4
  __int64 v76; // rcx
  int v77; // r8d
  int v78; // r9d
  PVOID *v79; // rax
  unsigned int v80; // eax
  unsigned int v81; // eax
  unsigned __int64 v82; // r14
  RdpRect *v83; // rax
  __int64 v84; // rcx
  RdpRect *v85; // r12
  __int64 v86; // rbx
  RdpRect *v87; // rsi
  RdpRect *v88; // rax
  __int64 v89; // rcx
  RdpRect *v90; // r12
  unsigned __int64 v91; // rbx
  RdpRect *i; // rsi
  RdpRect *v93; // rax
  __int64 v94; // rcx
  RdpRect *v95; // r12
  unsigned __int64 v96; // rbx
  RdpRect *j; // rsi
  void *v98; // rax
  __int64 v99; // rcx
  int v100; // eax
  int v101; // edx
  const char *v102; // rcx
  void *v103; // rax
  __int64 v104; // rcx
  _QWORD *v105; // rax
  unsigned int v106; // r8d
  unsigned __int8 v107; // r9
  unsigned int v108; // edx
  __int64 v109; // rcx
  unsigned int v110; // eax
  VCRectTracer *v111; // rcx
  __int64 v112; // rcx
  PEVENT_DATA_DESCRIPTOR UserData; // [rsp+28h] [rbp-D8h]
  unsigned int v115; // [rsp+30h] [rbp-D0h]
  const char **v116; // [rsp+30h] [rbp-D0h]
  const char **v117; // [rsp+40h] [rbp-C0h]
  const char **v118; // [rsp+48h] [rbp-B8h]
  const char *v119; // [rsp+60h] [rbp-A0h] BYREF
  const char *v120; // [rsp+68h] [rbp-98h] BYREF
  const char *v121; // [rsp+70h] [rbp-90h] BYREF
  const char *v122; // [rsp+78h] [rbp-88h] BYREF
  const char *v123; // [rsp+80h] [rbp-80h] BYREF
  const char *v124; // [rsp+88h] [rbp-78h] BYREF
  const char *v125; // [rsp+90h] [rbp-70h] BYREF
  const char *v126; // [rsp+98h] [rbp-68h] BYREF
  const char *v127; // [rsp+A0h] [rbp-60h] BYREF
  const char *v128; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v129; // [rsp+B0h] [rbp-50h] BYREF
  VARIANTARG pvarg; // [rsp+B8h] [rbp-48h] BYREF
  __int64 *v131; // [rsp+D0h] [rbp-30h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+D8h] [rbp-28h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v133; // [rsp+F0h] [rbp-10h] BYREF
  __int64 *v134; // [rsp+100h] [rbp+0h]
  int v135; // [rsp+108h] [rbp+8h]
  int v136; // [rsp+10Ch] [rbp+Ch]
  const char *v137; // [rsp+110h] [rbp+10h]
  __int64 v138; // [rsp+118h] [rbp+18h]
  const char **v139; // [rsp+120h] [rbp+20h]
  __int64 v140; // [rsp+128h] [rbp+28h]
  const char *v141; // [rsp+130h] [rbp+30h]
  __int64 v142; // [rsp+138h] [rbp+38h]
  const char **v143; // [rsp+140h] [rbp+40h]
  __int64 v144; // [rsp+148h] [rbp+48h]
  const char *v145; // [rsp+150h] [rbp+50h]
  __int64 v146; // [rsp+158h] [rbp+58h]
  const char **v147; // [rsp+160h] [rbp+60h]
  __int64 v148; // [rsp+168h] [rbp+68h]
  const char **v149; // [rsp+170h] [rbp+70h]
  __int64 v150; // [rsp+178h] [rbp+78h]

  v12 = a10;
  v123 = a11;
  v122 = a4;
  v128 = a3;
  v131 = a9;
  v119 = (const char *)a10;
  v129 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( !*(_DWORD *)(a2 + 8) || !*(_DWORD *)(a2 + 12) || !*(_DWORD *)(a2 + 16) || !*(_DWORD *)(a2 + 20) )
  {
    v25 = -2147024809;
    goto LABEL_180;
  }
  *((_DWORD *)this + 67) = (int)(float)(*(float *)(a2 + 24) + 0.5);
  v18 = *((_QWORD *)this + 12);
  if ( *a9 != v18 )
  {
    if ( v18 )
    {
      *((_QWORD *)this + 12) = 0;
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v18 + 32) + 16LL))(*(_QWORD *)(v18 + 32));
    }
    v18 = *a9;
    *((_QWORD *)this + 12) = *a9;
    if ( v18 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v18 + 32) + 8LL))(*(_QWORD *)(v18 + 32));
  }
  *((_DWORD *)this + 66) = a6;
  v19 = *a3;
  if ( *a3 == -1
    || (LODWORD(v18) = *((unsigned __int8 *)a3 + 1), (_BYTE)v18 == 0xFF)
    || v19 > 0x33u
    || (unsigned __int8)v18 > 0x33u
    || v19 < (unsigned __int8)v18 )
  {
    v25 = -2147024809;
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      LODWORD(v121) = 527;
      v128 = "No QP settings given to AVC codec, or QP outside of AVC spec range given.";
      v122 = "InitializeInput";
      v119 = "Error HResult failed";
      v123 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
      LODWORD(v120) = -2147024809;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v18,
        (unsigned int)&word_1801A156E,
        v16,
        v17,
        (__int64)&v119,
        (__int64)&v120,
        (__int64)&v123,
        (__int64)&v121,
        (__int64)&v122,
        (__int64)&v128);
    }
    goto LABEL_180;
  }
  *((_WORD *)this + 74) = *(_WORD *)a3;
  *((_BYTE *)this + 150) = a3[2];
  *((_DWORD *)this + 6) = *(_DWORD *)(a2 + 8);
  *((_DWORD *)this + 7) = *(_DWORD *)(a2 + 12);
  v20 = *(_DWORD *)(a2 + 16);
  *((_DWORD *)this + 8) = v20;
  v21 = *(_DWORD *)(a2 + 20);
  *((_DWORD *)this + 9) = v21;
  *((_DWORD *)this + 52) = *(_DWORD *)(a2 + 44);
  *((_DWORD *)this + 53) = *(_DWORD *)(a2 + 48);
  *((_DWORD *)this + 54) = *(_DWORD *)(a2 + 56);
  *((_DWORD *)this + 55) = *(_DWORD *)(a2 + 60);
  *((_DWORD *)this + 51) = *(_DWORD *)(a2 + 72);
  *((_DWORD *)this + 56) = *(_DWORD *)(a2 + 76);
  v22 = *(_DWORD *)(a2 + 16);
  if ( a8 )
    v23 = (v22 + 31) & 0xFFFFFFE0;
  else
    v23 = (v22 + 15) & 0xFFFFFFF0;
  *((_DWORD *)this + 10) = v23;
  v24 = (*(_DWORD *)(a2 + 20) + 15) & 0xFFFFFFF0;
  *((_DWORD *)this + 11) = v24;
  *((_DWORD *)this + 12) = v23 * v24;
  if ( v20 < v23 )
  {
    v25 = -2147024809;
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      LODWORD(v127) = 560;
      v119 = "Source frame width is less than Encoding frame width";
      v121 = "InitializeInput";
      v124 = "Error HResult failed";
      v120 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
      LODWORD(v126) = -2147024809;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v20,
        (unsigned int)&byte_1801A15BF,
        v23,
        v24,
        (__int64)&v124,
        (__int64)&v126,
        (__int64)&v120,
        (__int64)&v127,
        (__int64)&v121,
        (__int64)&v119);
    }
    goto LABEL_180;
  }
  if ( v23 < 0x40 || v24 < 0x40 || v23 > 0x1000 || v24 > 0x1000 || v23 * v24 > 0x900000 )
  {
    v25 = -2147024809;
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      LODWORD(v121) = 572;
      v128 = "Resolution is not within the bounds for AVC";
      v122 = "InitializeInput";
      v119 = "Error HResult failed";
      v123 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
      LODWORD(v120) = -2147024809;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v20,
        (unsigned int)byte_1801A151D,
        v23,
        v24,
        (__int64)&v119,
        (__int64)&v120,
        (__int64)&v123,
        (__int64)&v121,
        (__int64)&v122,
        (__int64)&v128);
    }
    goto LABEL_180;
  }
  OutputAvc = CreateOutputAvc(v20, v21, v23, v24);
  v27 = *((_DWORD *)this + 11) * *((_DWORD *)this + 10);
  *((_QWORD *)this + 20) = OutputAvc;
  *((_QWORD *)this + 14) = 0;
  v28 = v27 >> 8;
  *((_DWORD *)this + 36) = v28;
  v29 = operator new[](v28);
  *((_QWORD *)this + 15) = v29;
  if ( !v29 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_32;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(v30);
    v32 = 10;
    v33 = "BYTE";
LABEL_31:
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v32,
      (unsigned int)&WPP_1187df101f8d3e84b96b04ec6b6a0c86_Traceguids,
      ActivityIdPrefix,
      (__int64)v33);
LABEL_32:
    v25 = -2147024882;
    goto LABEL_180;
  }
  v34 = *((unsigned int *)this + 36);
  v35 = 2;
  *((_QWORD *)this + 16) = v29;
  *((_QWORD *)this + 17) = v29;
  memset_0(v29, 2, v34);
  v36 = *((unsigned int *)this + 56);
  LODWORD(v127) = v36;
  if ( a5 < (unsigned int)v36 )
  {
    v36 = a5;
    if ( a5 < 0x190 )
      v36 = 400;
    LODWORD(v127) = v36;
  }
  *((_DWORD *)this + 68) = v36;
  *((_DWORD *)this + 71) = a8;
  *((_DWORD *)this + 69) = 1000 * v36;
  *((_DWORD *)this + 70) = a7;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v37 = *(_DWORD *)a4;
    v38 = RdpX_GetActivityIdPrefix(v36);
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_1187df101f8d3e84b96b04ec6b6a0c86_Traceguids, v38, v37);
    v12 = (struct ID3D11ShaderResourceView *)v119;
  }
  if ( (unsigned int)(*(_DWORD *)a4 - 1) > 1 )
  {
    if ( *(_DWORD *)a4 == 3 )
    {
      v25 = AvcEncoder::InitializeMFTSwEncoder(this);
      if ( v25 < 0 )
      {
        if ( (unsigned int)dword_1801B76C8 > 2 )
        {
          v121 = "InitializeInput";
          v119 = "InitializeMFTSwEncoder failure";
          LODWORD(v127) = 688;
          v124 = "Error HResult failed";
          v120 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
          LODWORD(v126) = v25;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            dword_1801B76C8,
            (unsigned int)byte_1801A125B,
            v40,
            v41,
            (__int64)&v124,
            (__int64)&v126,
            (__int64)&v120,
            (__int64)&v127,
            (__int64)&v121,
            (__int64)&v119);
        }
        goto LABEL_180;
      }
      if ( (unsigned int)dword_1801B76C8 > 4 )
      {
        v119 = "AVC MFT software encoder successfully initialized.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v39,
          (unsigned int)byte_1801A1211,
          v40,
          v41,
          (__int64)&v119);
      }
    }
    goto LABEL_93;
  }
  v42 = (CMFApi *)*((_QWORD *)this + 12);
  LODWORD(v126) = 0;
  PreferredHwAdapterFromSRV = CMFApi::GetPreferredHwAdapterFromSRV(v42, v12, &v129, (enum PreferredHwVendor *)&v126);
  v44 = (unsigned int)v126;
  if ( PreferredHwAdapterFromSRV < 0 && (unsigned int)dword_1801B76C8 > 2 )
  {
    LODWORD(v126) = PreferredHwAdapterFromSRV;
    LODWORD(v120) = PreferredHwAdapterFromSRV;
    EventDescriptor.Keyword = 0;
    v149 = &v126;
    LODWORD(v125) = v44;
    v147 = &v125;
    LODWORD(v124) = 611;
    v143 = &v124;
    v150 = 4;
    v139 = &v120;
    v137 = "GetPreferredHwAdapterFromSRV failed";
    *(_DWORD *)&EventDescriptor.Level = 2;
    v133.Ptr = (ULONGLONG)off_1801B76D0;
    v148 = 4;
    v145 = "InitializeInput";
    v146 = 16;
    v144 = 4;
    v141 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
    v142 = 59;
    v140 = 4;
    v138 = 36;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    v133.Size = *(unsigned __int16 *)off_1801B76D0;
    v134 = qword_1801A14C8;
    v133.Reserved = 2;
    v135 = 84;
    v136 = 1;
    LODWORD(v121) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(qword_1801B76E8, &EventDescriptor, 0, 0, 9u, &v133);
  }
  v119 = 0;
  bstrVal = 0;
  if ( (**(int (__fastcall ***)(const char *, GUID *, const char **))v123)(v123, &IID_IRDPENCPlatformContext, &v119) >= 0
    && (*(int (__fastcall **)(const char *, const wchar_t *, VARIANTARG *))(*(_QWORD *)v119 + 24LL))(
         v119,
         L"WVD::AVCDriverVersionBlock",
         &pvarg) >= 0
    && pvarg.vt == 8 )
  {
    bstrVal = pvarg.bstrVal;
  }
  v25 = AdapterToEncoderCreator::Initialize((AvcEncoder *)((char *)this + 376), *((struct CMFApi **)this + 12), bstrVal);
  if ( v25 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_59;
    v124 = "InitializeInput";
    v123 = "AdapterToEncoderCreator::Initialize failed";
    v49 = (int *)byte_1801A141B;
    LODWORD(v121) = 625;
    v127 = "Error HResult failed";
    v118 = &v123;
    v117 = &v124;
    v116 = &v125;
    v50 = &v127;
    v125 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
    goto LABEL_58;
  }
  v25 = AvcEncoder::InitializeMFTHwEncoder(this, v44, v129);
  if ( v25 )
  {
    v46 = *((_QWORD *)this + 8);
    if ( v46 )
    {
      *((_QWORD *)this + 8) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
      *((_QWORD *)this + 8) = 0;
    }
    v52 = (char *)v122;
    if ( *(_DWORD *)v122 == 2 )
    {
      if ( v25 < 0 )
      {
        if ( (unsigned int)dword_1801B76C8 > 2 )
        {
          v123 = "InitializeInput";
          v122 = "create and initialize hardware encoder failed, and it is required";
          v49 = &dword_1801A146C;
          LODWORD(v121) = 637;
          v125 = "Error HResult failed";
          v118 = &v122;
          v117 = &v123;
          v116 = &v124;
          v50 = &v125;
          v124 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
LABEL_58:
          LODWORD(v120) = v25;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v46,
            (_DWORD)v49,
            v47,
            v48,
            (__int64)v50,
            (__int64)&v120,
            (__int64)v116,
            (__int64)&v121,
            (__int64)v117,
            (__int64)v118);
          goto LABEL_59;
        }
        goto LABEL_59;
      }
    }
    else
    {
      DefaultOrFallbackAvcEncoderInfo = AvcEncodeSettings::GetDefaultOrFallbackAvcEncoderInfo();
      *(_DWORD *)v52 = DefaultOrFallbackAvcEncoderInfo;
      if ( DefaultOrFallbackAvcEncoderInfo == 3 )
      {
        v54 = v25;
        v25 = AvcEncoder::InitializeMFTSwEncoder(this);
        if ( (unsigned int)dword_1801B76C8 > 4 )
        {
          LODWORD(v46) = qword_1801B76E0;
          if ( (qword_1801B76D8 & 0x470000000000LL) != 0 && (qword_1801B76E0 & 0x470000000000LL) == qword_1801B76E0 )
          {
            LODWORD(v121) = v25;
            v122 = (char *)this + 8;
            LODWORD(v120) = v54;
            v123 = "AVCEncoder";
            v124 = "Stack";
            v126 = "Checkpoint";
            v125 = (const char *)0x1000000;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              qword_1801B76E0,
              (unsigned int)word_1801A1322,
              v47,
              v48,
              (__int64)&v126,
              (__int64)&v125,
              (__int64)&v124,
              (__int64)&v123,
              (__int64)&v122,
              (__int64)&v120,
              (__int64)&v121);
          }
        }
        if ( v25 < 0 )
        {
          if ( (unsigned int)dword_1801B76C8 > 2 )
          {
            v123 = "InitializeInput";
            v122 = "Fallback to AVC MFT software encoder failed";
            v49 = (int *)word_1801A13CA;
            LODWORD(v121) = 660;
            v125 = "Error HResult failed";
            v118 = &v122;
            v117 = &v123;
            v116 = &v124;
            v50 = &v125;
            v124 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
            goto LABEL_58;
          }
LABEL_59:
          v51 = v119;
          if ( v119 )
          {
            v119 = 0;
            (*(void (__fastcall **)(const char *))(*(_QWORD *)v51 + 16LL))(v51);
          }
          goto LABEL_180;
        }
      }
      else if ( DefaultOrFallbackAvcEncoderInfo )
      {
        if ( v25 < 0 )
        {
          if ( (unsigned int)dword_1801B76C8 > 2 )
          {
            v123 = "InitializeInput";
            v122 = "Invalid AVC encoder setting detected while falling back to AVC SW mode";
            v49 = &dword_1801A12AC;
            LODWORD(v121) = 669;
            v125 = "Error HResult failed";
            v118 = &v122;
            v117 = &v123;
            v116 = &v124;
            v50 = &v125;
            v124 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
            goto LABEL_58;
          }
          goto LABEL_59;
        }
      }
      else
      {
        *((_DWORD *)this + 42) = 0;
        *((_DWORD *)this + 44) = 0;
      }
    }
  }
  else
  {
    v55 = (const wchar_t *)*((_QWORD *)this + 31);
    if ( v55
      && (wcsstr(v55, L"AMD") && *(_DWORD *)(a2 + 68)
       || wcsstr(*((const wchar_t **)this + 31), L"NVIDIA") && *(_DWORD *)(a2 + 64)) )
    {
      *((_DWORD *)this + 50) = 1;
      if ( (unsigned int)dword_1801B76C8 > 4 )
      {
        v122 = "AVC MFT hardware encoder use MF_EVENT_FLAG_NO_WAIT.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (_DWORD)v55,
          (unsigned int)byte_1801A12FD,
          v47,
          v48,
          (__int64)&v122);
      }
    }
    if ( (unsigned int)dword_1801B76C8 > 4 )
    {
      v122 = "AVC MFT hardware encoder successfully initialized.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (_DWORD)v55,
        (unsigned int)&word_1801A1236,
        v47,
        v48,
        (__int64)&v122);
    }
  }
  v56 = v119;
  if ( v119 )
  {
    v119 = 0;
    (*(void (__fastcall **)(const char *))(*(_QWORD *)v56 + 16LL))(v56);
  }
  v35 = 2;
LABEL_93:
  if ( *((_DWORD *)this + 42) )
  {
    v73 = a7;
  }
  else
  {
    v57 = operator new(0x3B8u);
    if ( v57 )
    {
      v57[2] = "AvcSoftWareEncoder";
      *((_DWORD *)v57 + 6) = -607474739;
      *((_DWORD *)v57 + 7) = 1;
      *v57 = &CClipLevelCallback::`vftable'{for `INonDelegatingUnknown'};
      v57[6] = 0;
      v57[1] = &CTSUnknown::`vftable'{for `CTSObject'};
      *v57 = &CClipLevelCallback::`vftable'{for `INonDelegatingUnknown'};
      *((_DWORD *)v57 + 10) = 0;
      v57[7] = 0;
      v57[8] = 0;
      v57[9] = 0;
      *((_DWORD *)v57 + 22) = 0;
      v57[1] = &AvcSoftWareEncoder::`vftable'{for `CTSObject'};
      v57[4] = v57;
      v57[10] = 1106247680;
      memset_0(&v133, 0, 0x138u);
      v58 = (struct _EVENT_DATA_DESCRIPTOR *)((char *)v57 + 92);
      v59 = &v133;
      do
      {
        v58 += 8;
        v60 = *v59;
        v61 = v59[1];
        v59 += 8;
        v58[-8] = v60;
        v62 = v59[-6];
        v58[-7] = v61;
        v63 = v59[-5];
        v58[-6] = v62;
        v64 = v59[-4];
        v58[-5] = v63;
        v65 = v59[-3];
        v58[-4] = v64;
        v66 = v59[-2];
        v58[-3] = v65;
        v67 = v59[-1];
        v58[-2] = v66;
        v58[-1] = v67;
        --v35;
      }
      while ( v35 );
      v68 = v59[1];
      *v58 = *v59;
      v69 = v59[2];
      Ptr = v59[3].Ptr;
      v58[1] = v68;
      v58[2] = v69;
      v58[3].Ptr = Ptr;
      v57[51] = 0;
      memset_0(v57 + 52, 0, 0x200u);
      v57[116] = 0;
      v57[117] = 0;
      *((_DWORD *)v57 + 236) = 0;
    }
    else
    {
      v57 = 0;
    }
    v71 = (_QWORD **)*((_QWORD *)this + 7);
    if ( v57 != v71 )
    {
      if ( v71 )
      {
        *((_QWORD *)this + 7) = 0;
        (*(void (__fastcall **)(_QWORD *))(*v71[4] + 16LL))(v71[4]);
      }
      *((_QWORD *)this + 7) = v57;
      if ( v57 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v57[4] + 8LL))(v57[4]);
    }
    v72 = (AvcSoftWareEncoder *)*((_QWORD *)this + 7);
    if ( !v72 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_32;
      }
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(v71);
      v32 = 12;
      v33 = "AvcSoftWareEncoder";
      goto LABEL_31;
    }
    v73 = a7;
    v133.Ptr = *(_QWORD *)a2;
    v133.Reserved = *((_DWORD *)this + 8);
    v134 = *(__int64 **)((char *)this + 36);
    v135 = *((_DWORD *)this + 11);
    v74 = 3;
    if ( !a7 )
      v74 = 1;
    v133.Size = 4;
    v136 = v74;
    HIDWORD(v142) = -1;
    LODWORD(v137) = a7 != 0 ? 0x10002 : 0;
    HIDWORD(v137) = *((unsigned __int8 *)v128 + 1);
    LODWORD(v138) = *(unsigned __int8 *)v128;
    if ( v128[2] != -1 )
      HIDWORD(v142) = *((unsigned __int8 *)v128 + 2);
    v75 = *(_DWORD *)(a2 + 24);
    HIDWORD(v138) = (_DWORD)v127;
    v139 = (const char **)__PAIR64__(v75, a6);
    if ( a7 )
      LODWORD(v140) = (a8 != 0) + 257;
    else
      LODWORD(v140) = 16;
    HIDWORD(v140) = *(_DWORD *)(a2 + 28);
    v141 = *(const char **)(a2 + 32);
    LODWORD(v142) = *(_DWORD *)(a2 + 40);
    LODWORD(v143) = *(_DWORD *)(a2 + 52);
    v25 = AvcSoftWareEncoder::InitializeAVC(v72, (struct AvcSoftWareEncoder::InitParams *)&v133);
    if ( v25 < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        v122 = "InitializeInput";
        v128 = "InitializeAVC failure";
        LODWORD(v121) = 731;
        v119 = "Error HResult failed";
        v123 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
        LODWORD(v120) = v25;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v76,
          (unsigned int)qword_1801A11C0,
          v77,
          v78,
          (__int64)&v119,
          (__int64)&v120,
          (__int64)&v123,
          (__int64)&v121,
          (__int64)&v122,
          (__int64)&v128);
      }
      goto LABEL_180;
    }
    v79 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v80 = RdpX_GetActivityIdPrefix(v76);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_1187df101f8d3e84b96b04ec6b6a0c86_Traceguids, v80);
      v79 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( (_DWORD)v141 && v79 != &WPP_GLOBAL_Control && (*((_DWORD *)v79 + 7) & 0x100) != 0 && *((_BYTE *)v79 + 25) >= 4u )
    {
      v81 = RdpX_GetActivityIdPrefix(v76);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_1187df101f8d3e84b96b04ec6b6a0c86_Traceguids, v81);
    }
  }
  v82 = *((_DWORD *)this + 12) >> 8;
  v83 = (RdpRect *)operator new[](saturated_mul(v82, 0x10u));
  v85 = v83;
  if ( !v83 )
  {
    *((_QWORD *)this + 36) = 0;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_32;
    }
    v100 = RdpX_GetActivityIdPrefix(v84);
    v101 = 15;
    v102 = "m_pRectsAll";
    goto LABEL_174;
  }
  v86 = (unsigned int)v82;
  v87 = v83;
  if ( v82 )
  {
    do
    {
      RdpRect::RdpRect(v87);
      v87 = (RdpRect *)((char *)v87 + 16);
      --v86;
    }
    while ( v86 );
  }
  *((_QWORD *)this + 36) = v85;
  v88 = (RdpRect *)operator new[](saturated_mul(v82, 0x10u));
  v90 = v88;
  if ( !v88 )
  {
    *((_QWORD *)this + 38) = 0;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_32;
    }
    v100 = RdpX_GetActivityIdPrefix(v89);
    v101 = 16;
    v102 = "m_pRectsDirt";
    goto LABEL_174;
  }
  v91 = v82;
  for ( i = v88; v91; --v91 )
  {
    RdpRect::RdpRect(i);
    i = (RdpRect *)((char *)i + 16);
  }
  *((_QWORD *)this + 38) = v90;
  v93 = (RdpRect *)operator new[](saturated_mul(v82, 0x10u));
  v95 = v93;
  if ( !v93 )
  {
    *((_QWORD *)this + 37) = 0;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_32;
    }
    v100 = RdpX_GetActivityIdPrefix(v94);
    v101 = 17;
    v102 = "m_pRectsProg";
    goto LABEL_174;
  }
  v96 = v82;
  for ( j = v93; v96; --v96 )
  {
    RdpRect::RdpRect(j);
    j = (RdpRect *)((char *)j + 16);
  }
  *((_QWORD *)this + 37) = v95;
  v98 = o_malloc_0(v82);
  *((_QWORD *)this + 39) = v98;
  if ( !v98 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_32;
    }
    v100 = RdpX_GetActivityIdPrefix(v99);
    v101 = 18;
    v102 = "m_pQPProg";
LABEL_174:
    LODWORD(UserData) = -2147024882;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v101,
      (unsigned int)&WPP_1187df101f8d3e84b96b04ec6b6a0c86_Traceguids,
      v100,
      (__int64)v102,
      UserData);
    v25 = -2147024882;
    goto LABEL_180;
  }
  v103 = o_malloc_0(v82);
  *((_QWORD *)this + 40) = v103;
  if ( !v103 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_32;
    }
    v100 = RdpX_GetActivityIdPrefix(v104);
    v101 = 19;
    v102 = "m_pQPDirt";
    goto LABEL_174;
  }
  *((_DWORD *)this + 88) = v82;
  *((_DWORD *)this + 87) = v82;
  *((_DWORD *)this + 89) = v82;
  v105 = operator new(0x60u);
  if ( !v105 )
  {
    *((_QWORD *)this + 46) = 0;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_32;
    }
    v100 = RdpX_GetActivityIdPrefix(0);
    v101 = 21;
    v102 = "m_pAvcTracer";
    goto LABEL_174;
  }
  v105[1] = 0;
  *(_DWORD *)v105 = 25;
  *((_BYTE *)v105 + 4) = -2;
  *((_DWORD *)v105 + 4) = 0;
  v105[3] = 0;
  *((_DWORD *)v105 + 8) = 0;
  v105[5] = 0;
  v105[6] = 0;
  v105[7] = 0;
  v105[8] = 0;
  *((_WORD *)v105 + 36) = 0;
  v105[10] = 0;
  *((_DWORD *)v105 + 22) = 0;
  v107 = *((_BYTE *)this + 149);
  *((_QWORD *)this + 46) = v105;
  if ( (int)VCRectTracer::Initialize(
              (VCRectTracer *)v105,
              v73,
              v106,
              v107,
              *((_BYTE *)this + 148),
              *((_DWORD *)this + 10),
              v115,
              *((_DWORD *)this + 36)) < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v110 = RdpX_GetActivityIdPrefix(v109);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_1187df101f8d3e84b96b04ec6b6a0c86_Traceguids, v110);
    }
    v111 = (VCRectTracer *)*((_QWORD *)this + 46);
    if ( v111 )
      VCRectTracer::`scalar deleting destructor'(v111, v108);
    *((_QWORD *)this + 46) = 0;
  }
  v25 = 0;
LABEL_180:
  VariantClear(&pvarg);
  v112 = *v131;
  if ( *v131 )
  {
    *v131 = 0;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v112 + 32) + 16LL))(*(_QWORD *)(v112 + 32));
  }
  return (unsigned int)v25;
}

```

## disassembly

```asm
0x180089330  push    rbp
0x180089332  push    rbx
0x180089333  push    rsi
0x180089334  push    rdi
0x180089335  push    r12
0x180089337  push    r13
0x180089339  push    r14
0x18008933b  push    r15
0x18008933d  lea     rbp, [rsp-148h]
0x180089345  sub     rsp, 248h
0x18008934c  mov     rax, cs:__security_cookie
0x180089353  xor     rax, rsp
0x180089356  mov     [rbp+180h+var_50], rax
0x18008935d  mov     rax, [rbp+180h+arg_50]
0x180089364  mov     rdi, rcx
0x180089367  mov     r12, [rbp+180h+arg_40]
0x18008936e  lea     rcx, [rbp+180h+pvarg]; pvarg
0x180089372  mov     rbx, [rbp+180h+arg_48]
0x180089379  xorps   xmm0, xmm0
0x18008937c  mov     [rbp+180h+var_200], rax
0x180089380  xor     r13d, r13d
0x180089383  xor     eax, eax
0x180089385  mov     [rsp+280h+var_208], r9
0x18008938a  mov     qword ptr [rbp+180h+pvarg+10h], rax
0x18008938e  mov     r14, r9
0x180089391  mov     r15, r8
0x180089394  mov     [rbp+180h+var_1D8], r8
0x180089398  mov     rsi, rdx
0x18008939b  mov     [rbp+180h+var_1B0], r12
0x18008939f  mov     [rsp+280h+var_220], rbx
0x1800893a4  mov     [rbp+180h+var_1D0], r13
0x1800893a8  movups  xmmword ptr [rbp+180h+pvarg], xmm0
0x1800893ac  call    cs:__imp_VariantInit
0x1800893b2  cmp     [rsi+8], r13d
0x1800893b6  jz      loc_18008A6D9
0x1800893bc  cmp     [rsi+0Ch], r13d
0x1800893c0  jz      loc_18008A6D9
0x1800893c6  cmp     [rsi+10h], r13d
0x1800893ca  jz      loc_18008A6D9
0x1800893d0  cmp     [rsi+14h], r13d
0x1800893d4  jz      loc_18008A6D9
0x1800893da  movss   xmm0, dword ptr [rsi+18h]
0x1800893df  addss   xmm0, cs:__real@3f000000
0x1800893e7  cvttss2si rax, xmm0
0x1800893ec  mov     [rdi+10Ch], eax
0x1800893f2  mov     rcx, [rdi+60h]
0x1800893f6  cmp     [r12], rcx
0x1800893fa  jz      short loc_180089432
0x1800893fc  test    rcx, rcx
0x1800893ff  jz      short loc_180089415
0x180089401  mov     [rdi+60h], r13
0x180089405  mov     rcx, [rcx+20h]
0x180089409  mov     rax, [rcx]
0x18008940c  mov     rax, [rax+10h]
0x180089410  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089415  mov     rcx, [r12]
0x180089419  mov     [rdi+60h], rcx
0x18008941d  test    rcx, rcx
0x180089420  jz      short loc_180089432
0x180089422  mov     rcx, [rcx+20h]
0x180089426  mov     rax, [rcx]
0x180089429  mov     rax, [rax+8]
0x18008942d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089432  mov     eax, [rbp+180h+arg_28]
0x180089438  mov     [rdi+108h], eax
0x18008943e  movzx   eax, byte ptr [r15]
0x180089442  cmp     al, 0FFh
0x180089444  jz      loc_18008A643
0x18008944a  movzx   ecx, byte ptr [r15+1]
0x18008944f  cmp     cl, 0FFh
0x180089452  jz      loc_18008A643
0x180089458  cmp     al, 33h ; '3'
0x18008945a  ja      loc_18008A643
0x180089460  cmp     cl, 33h ; '3'
0x180089463  ja      loc_18008A643
0x180089469  cmp     al, cl
0x18008946b  jb      loc_18008A643
0x180089471  movzx   eax, word ptr [r15]
0x180089475  mov     [rdi+94h], ax
0x18008947c  movzx   eax, byte ptr [r15+2]
0x180089481  mov     r15d, [rbp+180h+arg_38]
0x180089488  mov     [rdi+96h], al
0x18008948e  mov     eax, [rsi+8]
0x180089491  mov     [rdi+18h], eax
0x180089494  mov     eax, [rsi+0Ch]
0x180089497  mov     [rdi+1Ch], eax
0x18008949a  mov     ecx, [rsi+10h]; int
0x18008949d  mov     [rdi+20h], ecx
0x1800894a0  mov     edx, [rsi+14h]; int
0x1800894a3  mov     [rdi+24h], edx
0x1800894a6  mov     eax, [rsi+2Ch]
0x1800894a9  mov     [rdi+0D0h], eax
0x1800894af  mov     eax, [rsi+30h]
0x1800894b2  mov     [rdi+0D4h], eax
0x1800894b8  mov     eax, [rsi+38h]
0x1800894bb  mov     [rdi+0D8h], eax
0x1800894c1  mov     eax, [rsi+3Ch]
0x1800894c4  mov     [rdi+0DCh], eax
0x1800894ca  mov     eax, [rsi+48h]
0x1800894cd  mov     [rdi+0CCh], eax
0x1800894d3  mov     eax, [rsi+4Ch]
0x1800894d6  mov     [rdi+0E0h], eax
0x1800894dc  mov     r8d, [rsi+10h]
0x1800894e0  test    r15d, r15d
0x1800894e3  jz      short loc_1800894EF
0x1800894e5  add     r8d, 1Fh
0x1800894e9  and     r8d, 0FFFFFFE0h
0x1800894ed  jmp     short loc_1800894F7
0x1800894ef  add     r8d, 0Fh
0x1800894f3  and     r8d, 0FFFFFFF0h; int
0x1800894f7  mov     [rdi+28h], r8d
0x1800894fb  mov     r9d, [rsi+14h]
0x1800894ff  add     r9d, 0Fh
0x180089503  and     r9d, 0FFFFFFF0h; int
0x180089507  mov     eax, r9d
0x18008950a  mov     [rdi+2Ch], r9d
0x18008950e  imul    eax, r8d
0x180089512  mov     [rdi+30h], eax
0x180089515  cmp     ecx, r8d
0x180089518  jnb     loc_1800895B5
0x18008951e  mov     eax, cs:dword_1801B76C8
0x180089524  mov     ebx, 80070057h
0x180089529  cmp     eax, 2
0x18008952c  jbe     loc_18008A6DE
0x180089532  lea     rax, aSourceFrameWid
0x180089539  mov     dword ptr [rbp+180h+var_1E0], 230h
0x180089540  mov     [rsp+280h+var_220], rax
0x180089545  lea     r14, aInitializeinpu
0x18008954c  lea     rax, aErrorHresultFa
0x180089553  mov     [rsp+280h+var_210], r14
0x180089558  mov     [rbp+180h+var_1F8], rax
0x18008955c  lea     r12, aOnecoreuapTerm_2
0x180089563  lea     rax, [rsp+280h+var_220]
0x180089568  mov     [rsp+280h+var_218], r12
0x18008956d  mov     [rsp+280h+var_238], rax
0x180089572  lea     rdx, byte_1801A15BF
0x180089579  lea     rax, [rsp+280h+var_210]
0x18008957e  mov     dword ptr [rbp+180h+var_1E8], ebx
0x180089581  mov     [rsp+280h+var_240], rax
0x180089586  lea     rax, [rbp+180h+var_1E0]
0x18008958a  mov     qword ptr [rsp+280h+var_248], rax
0x18008958f  lea     rax, [rsp+280h+var_218]
0x180089594  mov     [rsp+280h+var_250], rax
0x180089599  lea     rax, [rbp+180h+var_1E8]
0x18008959d  mov     [rsp+280h+UserData], rax
0x1800895a2  lea     rax, [rbp+180h+var_1F8]
0x1800895a6  mov     qword ptr [rsp+280h+UserDataCount], rax
0x1800895ab  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z
0x1800895b0  jmp     loc_18008A6DE
0x1800895b5  cmp     r8d, 40h ; '@'
0x1800895b9  jb      loc_18008A5AA
0x1800895bf  cmp     r9d, 40h ; '@'
0x1800895c3  jb      loc_18008A5AA
0x1800895c9  cmp     r8d, 1000h
0x1800895d0  ja      loc_18008A5AA
0x1800895d6  cmp     r9d, 1000h
0x1800895dd  ja      loc_18008A5AA
0x1800895e3  cmp     eax, 900000h
0x1800895e8  ja      loc_18008A5AA
0x1800895ee  call    CreateOutputAvc
0x1800895f3  mov     ecx, [rdi+28h]
0x1800895f6  imul    ecx, [rdi+2Ch]
0x1800895fa  mov     [rdi+0A0h], rax
0x180089601  mov     [rdi+70h], r13
0x180089605  shr     ecx, 8; unsigned __int64
0x180089608  mov     [rdi+90h], ecx
0x18008960e  call    ??_U@YAPEAX_K@Z
0x180089613  mov     [rdi+78h], rax
0x180089617  test    rax, rax
0x18008961a  jnz     short loc_180089676
0x18008961c  mov     rax, cs:WPP_GLOBAL_Control
0x180089623  lea     r15, WPP_GLOBAL_Control
0x18008962a  cmp     rax, r15
0x18008962d  jz      short loc_18008966C
0x18008962f  test    byte ptr [rax+1Ch], 8
0x180089633  jz      short loc_18008966C
0x180089635  cmp     byte ptr [rax+19h], 2
0x180089639  jb      short loc_18008966C
0x18008963b  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180089641  mov     edx, 0Ah
0x180089646  lea     rcx, aByte
0x18008964d  mov     qword ptr [rsp+280h+UserDataCount], rcx
0x180089652  lea     r8, WPP_1187df101f8d3e84b96b04ec6b6a0c86_Traceguids
0x180089659  mov     rcx, cs:WPP_GLOBAL_Control
0x180089660  mov     r9d, eax
0x180089663  mov     rcx, [rcx+10h]
0x180089667  call    WPP_SF_Ds
0x18008966c  mov     ebx, 8007000Eh
0x180089671  jmp     loc_18008A6DE
0x180089676  mov     r8d, [rdi+90h]; Size
0x18008967d  mov     r13d, 2
0x180089683  mov     edx, r13d; Val
0x180089686  mov     [rdi+80h], rax
0x18008968d  mov     rcx, rax; void *
0x180089690  mov     [rdi+88h], rax
0x180089697  call    memset_0
0x18008969c  mov     ecx, [rdi+0E0h]
0x1800896a2  mov     eax, [rbp+180h+arg_20]
0x1800896a8  mov     dword ptr [rbp+180h+var_1E0], ecx
0x1800896ab  cmp     eax, ecx
0x1800896ad  jnb     short loc_1800896BE
0x1800896af  mov     edx, 190h
0x1800896b4  mov     ecx, eax
0x1800896b6  cmp     eax, edx
0x1800896b8  cmovb   ecx, edx
0x1800896bb  mov     dword ptr [rbp+180h+var_1E0], ecx
0x1800896be  imul    eax, ecx, 3E8h
0x1800896c4  mov     [rdi+110h], ecx
0x1800896ca  mov     [rdi+11Ch], r15d
0x1800896d1  mov     [rdi+114h], eax
0x1800896d7  mov     eax, [rbp+180h+arg_30]
0x1800896dd  mov     [rdi+118h], eax
0x1800896e3  mov     rax, cs:WPP_GLOBAL_Control
0x1800896ea  lea     r15, WPP_GLOBAL_Control
0x1800896f1  cmp     rax, r15
0x1800896f4  jz      short loc_180089736
0x1800896f6  test    dword ptr [rax+1Ch], 100h
0x1800896fd  jz      short loc_180089736
0x1800896ff  cmp     byte ptr [rax+19h], 4
0x180089703  jb      short loc_180089736
0x180089705  mov     ebx, [r14]
0x180089708  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18008970e  mov     rcx, cs:WPP_GLOBAL_Control
0x180089715  lea     r8, WPP_1187df101f8d3e84b96b04ec6b6a0c86_Traceguids
0x18008971c  mov     edx, 0Bh
0x180089721  mov     [rsp+280h+UserDataCount], ebx
0x180089725  mov     r9d, eax
0x180089728  mov     rcx, [rcx+10h]
0x18008972c  call    WPP_SF_Dd
0x180089731  mov     rbx, [rsp+280h+var_220]
0x180089736  mov     ecx, [r14]
0x180089739  lea     r12, aOnecoreuapTerm_2
0x180089740  lea     r14, aInitializeinpu
0x180089747  lea     eax, [rcx-1]
0x18008974a  cmp     eax, 1
0x18008974d  jbe     loc_180089828
0x180089753  cmp     ecx, 3
0x180089756  jnz     loc_180089DF9
0x18008975c  mov     rcx, rdi; this
0x18008975f  call    ?InitializeMFTSwEncoder@AvcEncoder@@AEAAJXZ
0x180089764  mov     ebx, eax
0x180089766  test    eax, eax
0x180089768  jns     loc_1800897F2
0x18008976e  mov     ecx, cs:dword_1801B76C8
0x180089774  cmp     ecx, r13d
0x180089777  jbe     loc_18008A6DE
0x18008977d  lea     rax, aInitializemfts
0x180089784  mov     [rsp+280h+var_210], r14
0x180089789  mov     [rsp+280h+var_220], rax
0x18008978e  lea     rdx, byte_1801A125B
0x180089795  lea     rax, aErrorHresultFa
0x18008979c  mov     dword ptr [rbp+180h+var_1E0], 2B0h
0x1800897a3  mov     [rbp+180h+var_1F8], rax
0x1800897a7  lea     rax, [rsp+280h+var_220]
0x1800897ac  mov     [rsp+280h+var_238], rax
0x1800897b1  lea     rax, [rsp+280h+var_210]
0x1800897b6  mov     [rsp+280h+var_240], rax
0x1800897bb  lea     rax, [rbp+180h+var_1E0]
0x1800897bf  mov     qword ptr [rsp+280h+var_248], rax
0x1800897c4  lea     rax, [rsp+280h+var_218]
0x1800897c9  mov     [rsp+280h+var_250], rax
0x1800897ce  lea     rax, [rbp+180h+var_1E8]
0x1800897d2  mov     [rsp+280h+UserData], rax
0x1800897d7  lea     rax, [rbp+180h+var_1F8]
0x1800897db  mov     qword ptr [rsp+280h+UserDataCount], rax
0x1800897e0  mov     [rsp+280h+var_218], r12
0x1800897e5  mov     dword ptr [rbp+180h+var_1E8], ebx
0x1800897e8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z
0x1800897ed  jmp     loc_18008A6DE
0x1800897f2  mov     eax, cs:dword_1801B76C8
0x1800897f8  cmp     eax, 4
0x1800897fb  jbe     loc_180089DF9
0x180089801  lea     rax, aAvcMftSoftware
0x180089808  mov     [rsp+280h+var_220], rax
0x18008980d  lea     rdx, byte_1801A1211
0x180089814  lea     rax, [rsp+280h+var_220]
0x180089819  mov     qword ptr [rsp+280h+UserDataCount], rax
0x18008981e  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z
0x180089823  jmp     loc_180089DF9
0x180089828  mov     rcx, [rdi+60h]; this
0x18008982c  lea     r9, [rbp+180h+var_1E8]; enum PreferredHwVendor *
0x180089830  lea     r8, [rbp+180h+var_1D0]; unsigned __int64 *
0x180089834  mov     dword ptr [rbp+180h+var_1E8], 0
0x18008983b  mov     rdx, rbx; struct ID3D11ShaderResourceView *
0x18008983e  call    ?GetPreferredHwAdapterFromSRV@CMFApi@@QEAAJPEAUID3D11ShaderResourceView@@PEA_KAEAW4PreferredHwVendor@@@Z
0x180089843  mov     r13d, dword ptr [rbp+180h+var_1E8]
0x180089847  test    eax, eax
0x180089849  jns     loc_180089964
0x18008984f  mov     ecx, cs:dword_1801B76C8
0x180089855  cmp     ecx, 2
0x180089858  jbe     loc_180089964
0x18008985e  mov     dword ptr [rbp+180h+var_1E8], eax
0x180089861  lea     rdx, [rbp+180h+EventDescriptor]; EventDescriptor
0x180089865  mov     dword ptr [rsp+280h+var_218], eax
0x180089869  xor     ecx, ecx
0x18008986b  mov     [rbp+180h+EventDescriptor.Keyword], rcx
0x18008986f  lea     rax, [rbp+180h+var_1E8]
0x180089873  mov     [rbp+180h+var_110], rax
0x180089877  lea     rcx, _TraceLoggingMetadata
0x18008987e  mov     dword ptr [rbp+180h+var_1F0], r13d
  ... truncated ...
```
