# Rdp::Avenc::Ic3::CDsStreamSource::Start(ds::nanocom::IStreamProcessor::StartParameters *,ds::nanocom::IStreamProcessingSession * *)

- ea: `0x180050c50`
- end: `0x1800514b2`
- name: `?Start@CDsStreamSource@Ic3@Avenc@Rdp@@UEAAJPEAUStartParameters@IStreamProcessor@nanocom@ds@@PEAPEAUIStreamProcessingSession@78@@Z`
- size: `2146`
- prototype: `__int64 __fastcall(Rdp::Avenc::Ic3::CDsStreamSource *__hidden this, struct ds::nanocom::IStreamProcessor::StartParameters *, struct ds::nanocom::IStreamProcessingSession **)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001114`
- `0x18000406c`
- `0x180006580`
- `0x1800065a4`
- `0x18000e848`
- `0x18000ec04`
- `0x18000ed7c`
- `0x1800103c0`
- `0x180010bc8`
- `0x1800146bc`
- `0x180048fc4`
- `0x180049198`
- `0x18004cf60`
- `0x18004e7a0`
- `0x180050518`
- `0x180050c50`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800513ff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800513ff`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180050c9b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180051413`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180050c9b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180051413`

## string_xrefs

- `0x18005149f`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180050cd7`: `Stream source is already started`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Rdp::Avenc::Ic3::CDsStreamSource::Start(
        Rdp::Avenc::Ic3::CDsStreamSource *this,
        struct ds::nanocom::IStreamProcessor::StartParameters *a2,
        struct ds::nanocom::IStreamProcessingSession **a3)
{
  int v6; // r8d
  int v7; // r9d
  __int64 v8; // rdx
  __int64 (__fastcall *v9)(struct ds::nanocom::IStreamProcessor::StartParameters *, char *); // r13
  struct ds::nanocom::IStreamFormat **v10; // r14
  _QWORD *v11; // rcx
  unsigned int v12; // eax
  __int64 v13; // rax
  unsigned int v14; // eax
  __int64 v15; // rax
  __int64 v16; // r15
  __int64 v17; // rcx
  __int64 v18; // rcx
  struct ID3D11Device *v19; // rdx
  int v20; // eax
  __int64 v21; // rdx
  __int64 (__fastcall ***v22)(_QWORD, GUID *, struct ds::nanocom::IStreamProcessingSession **); // rcx
  int v23; // eax
  int DxgiFormatFromStreamFormat; // r15d
  struct ds::nanocom::IStreamFormat *v25; // rcx
  __int64 (__fastcall *v26)(struct ds::nanocom::IStreamFormat *, __int128 *, __int64 *); // rax
  int v27; // eax
  int v28; // ecx
  int v29; // eax
  int v30; // ecx
  int v31; // ecx
  int v32; // ecx
  const char *v33; // r8
  const char *v34; // r9
  __int64 v35; // rdx
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rcx
  const char *v40; // r9
  __int64 result; // rax
  int v42; // [rsp+20h] [rbp-218h]
  int v43; // [rsp+20h] [rbp-218h]
  int v44; // [rsp+20h] [rbp-218h]
  char *v45; // [rsp+28h] [rbp-210h]
  char *v46; // [rsp+28h] [rbp-210h]
  char *v47; // [rsp+30h] [rbp-208h]
  char *v48; // [rsp+30h] [rbp-208h]
  int v49; // [rsp+60h] [rbp-1D8h] BYREF
  int v50; // [rsp+64h] [rbp-1D4h] BYREF
  char v51[4]; // [rsp+68h] [rbp-1D0h] BYREF
  int v52; // [rsp+6Ch] [rbp-1CCh] BYREF
  __int64 v53; // [rsp+70h] [rbp-1C8h] BYREF
  Rdp::Avenc::Ic3::CDsSourceStreamProcessingSession *v54; // [rsp+78h] [rbp-1C0h] BYREF
  const char *v55; // [rsp+80h] [rbp-1B8h] BYREF
  char v56[8]; // [rsp+88h] [rbp-1B0h] BYREF
  _QWORD v57[2]; // [rsp+90h] [rbp-1A8h] BYREF
  __int128 v58; // [rsp+A0h] [rbp-198h] BYREF
  int v59; // [rsp+B0h] [rbp-188h] BYREF
  int v60; // [rsp+B4h] [rbp-184h] BYREF
  int v61; // [rsp+B8h] [rbp-180h] BYREF
  int v62; // [rsp+BCh] [rbp-17Ch] BYREF
  struct ds::nanocom::IStreamProcessingSession::ICallback *v63[2]; // [rsp+C0h] [rbp-178h] BYREF
  char v64; // [rsp+D0h] [rbp-168h]
  GUID ActivityId; // [rsp+D8h] [rbp-160h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v66; // [rsp+F0h] [rbp-148h] BYREF
  const char *v67; // [rsp+110h] [rbp-128h]
  __int64 v68; // [rsp+118h] [rbp-120h]
  int *v69; // [rsp+120h] [rbp-118h]
  __int64 v70; // [rsp+128h] [rbp-110h]
  const char *v71; // [rsp+130h] [rbp-108h]
  __int64 v72; // [rsp+138h] [rbp-100h]
  const char *v73; // [rsp+140h] [rbp-F8h]
  __int64 v74; // [rsp+148h] [rbp-F0h]
  int *v75; // [rsp+150h] [rbp-E8h]
  __int64 v76; // [rsp+158h] [rbp-E0h]
  int *v77; // [rsp+160h] [rbp-D8h]
  __int64 v78; // [rsp+168h] [rbp-D0h]
  __int64 v79; // [rsp+170h] [rbp-C8h]
  __int64 v80; // [rsp+178h] [rbp-C0h]
  const char *v81; // [rsp+180h] [rbp-B8h]
  int v82; // [rsp+188h] [rbp-B0h]
  int v83; // [rsp+18Ch] [rbp-ACh]
  const char *v84; // [rsp+190h] [rbp-A8h]
  int v85; // [rsp+198h] [rbp-A0h]
  int v86; // [rsp+19Ch] [rbp-9Ch]
  int *v87; // [rsp+1A0h] [rbp-98h]
  __int64 v88; // [rsp+1A8h] [rbp-90h]
  int *v89; // [rsp+1B0h] [rbp-88h]
  __int64 v90; // [rsp+1B8h] [rbp-80h]
  int *v91; // [rsp+1C0h] [rbp-78h]
  __int64 v92; // [rsp+1C8h] [rbp-70h]
  int *v93; // [rsp+1D0h] [rbp-68h]
  __int64 v94; // [rsp+1D8h] [rbp-60h]
  char *v95; // [rsp+1E0h] [rbp-58h]
  __int64 v96; // [rsp+1E8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+0h]

  ActivityId = *(GUID *)&xmmword_1800C21A0;
  EventActivityIdControl(4u, &ActivityId);
  try
  {
    if ( !a2 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x12F,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\dsstreamsource.cpp",
        (const char *)0x80004003LL,
        v42);
    if ( !a3 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x130,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\dsstreamsource.cpp",
        (const char *)0x80004003LL,
        v42);
    LOBYTE(v42) = *((_QWORD *)this + 27) != 0;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x131,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\dsstreamsource.cpp",
      (const char *)0x8000FFFFLL,
      v42,
      (bool)"Stream source is already started",
      v47);
    v63[1] = (Rdp::Avenc::Ic3::CDsStreamSource *)((char *)this + 48);
    v64 = 0;
    if ( (unsigned int)mtx_do_lock((__int64)this + 48) )
      std::_Throw_Cpp_error(5);
    if ( *((_DWORD *)this + 31) == 0x7FFFFFFF )
    {
      *((_DWORD *)this + 31) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    v64 = 1;
    if ( (unsigned int)dword_1800C1058 > 5 )
    {
      v8 = *((_QWORD *)this + 17);
      v54 = (Rdp::Avenc::Ic3::CDsSourceStreamProcessingSession *)(v8 + 112);
      v49 = *(_DWORD *)(*(_QWORD *)(v8 + 104) + 136LL);
      v50 = *(_DWORD *)(v8 + 128);
      v57[0] = "Start";
      *(_QWORD *)v56 = "Rdp::Avenc::Ic3::CDsStreamSource::Start";
      *(_DWORD *)v51 = 315;
      v55 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\dsstreamsource.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)byte_1800B299D,
        v6,
        v7,
        (__int64)&v55,
        (__int64)v51,
        (__int64)v56,
        (__int64)v57,
        (__int64)&v50,
        (__int64)&v49,
        (__int64)&v54);
    }
    v9 = *(__int64 (__fastcall **)(struct ds::nanocom::IStreamProcessor::StartParameters *, char *))(*(_QWORD *)a2 + 32LL);
    v10 = (struct ds::nanocom::IStreamFormat **)((char *)this + 152);
    v11 = (_QWORD *)*((_QWORD *)this + 19);
    *((_QWORD *)this + 19) = 0;
    if ( v11 )
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v11 + 16LL))(v11, *v11);
    v12 = v9(a2, (char *)this + 152);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x13E,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\dsstreamsource.cpp",
      (const char *)v12,
      (int)"Failed to get output stream format from stream processor start parameters",
      v45);
    LOBYTE(v43) = *v10 == 0;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x13F,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\dsstreamsource.cpp",
      (const char *)0x8000FFFFLL,
      v43,
      (bool)"Failed to get non-nullptr output stream format from stream processor start parameters",
      v48);
    v13 = *(_QWORD *)a2;
    v63[0] = 0;
    v14 = (*(__int64 (__fastcall **)(struct ds::nanocom::IStreamProcessor::StartParameters *, struct ds::nanocom::IStreamProcessingSession::ICallback **))(v13 + 40))(
            a2,
            v63);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x143,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\dsstreamsource.cpp",
      (const char *)v14,
      (int)"Failed to get callback from stream processor start parameters",
      v46);
    v54 = (Rdp::Avenc::Ic3::CDsSourceStreamProcessingSession *)operator new(0xF8u);
    v15 = Rdp::Avenc::Ic3::CDsSourceStreamProcessingSession::CDsSourceStreamProcessingSession(
            v54,
            *((struct Rdp::Avenc::Ic3::CMonitorContext **)this + 17),
            *v10,
            v63[0]);
    v16 = *((_QWORD *)this + 27);
    *((_QWORD *)this + 27) = v15;
    if ( v15 )
    {
      v17 = v15 + 8 + *(int *)(*(_QWORD *)(v15 + 8) + 4LL);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
    }
    if ( v16 )
    {
      v18 = v16 + *(int *)(*(_QWORD *)(v16 + 8) + 4LL) + 8LL;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    v19 = (struct ID3D11Device *)*((_QWORD *)this + 16);
    if ( v19 )
    {
      v20 = Rdp::Avenc::Ic3::CDsSourceStreamProcessingSession::SetEncodeDevice(
              *((Rdp::Avenc::Ic3::CDsSourceStreamProcessingSession **)this + 27),
              v19);
      if ( v20 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x14B,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\dsstreamsource.cpp",
          (const char *)(unsigned int)v20,
          v44);
    }
    v21 = *((_QWORD *)this + 27);
    if ( v21 )
    {
      v22 = (__int64 (__fastcall ***)(_QWORD, GUID *, struct ds::nanocom::IStreamProcessingSession **))(v21 + 8 + *(int *)(*(_QWORD *)(v21 + 8) + 4LL));
      v23 = (**v22)(v22, &GUID_e6567424_d3ae_5566_6f43_31760af27908, a3);
      if ( v23 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x1CBE,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
          (const char *)(unsigned int)v23,
          v44);
    }
    else
    {
      *a3 = 0;
    }
    DxgiFormatFromStreamFormat = anonymous_namespace_::GetDxgiFormatFromStreamFormat(*v10);
    v53 = 0;
    v25 = *v10;
    v26 = *(__int64 (__fastcall **)(struct ds::nanocom::IStreamFormat *, __int128 *, __int64 *))(*(_QWORD *)*v10 + 40LL);
    v53 = 0;
    v58 = xmmword_18009A2D0;
    v27 = v26(v25, &v58, &v53);
    v57[0] = 0;
    *(_QWORD *)v56 = 0;
    v55 = 0;
    v54 = 0;
    if ( v27 >= 0 && v53 )
    {
      v58 = xmmword_18009A250;
      (*(void (__fastcall **)(__int64, __int128 *, Rdp::Avenc::Ic3::CDsSourceStreamProcessingSession **))(*(_QWORD *)v53 + 32LL))(
        v53,
        &v58,
        &v54);
      v58 = xmmword_18009A2B8;
      (*(void (__fastcall **)(__int64, __int128 *, _QWORD *))(*(_QWORD *)v53 + 32LL))(v53, &v58, v57);
      v58 = xmmword_18009A260;
      (*(void (__fastcall **)(__int64, __int128 *, char *))(*(_QWORD *)v53 + 32LL))(v53, &v58, v56);
      v58 = xmmword_18009A240;
      (*(void (__fastcall **)(__int64, __int128 *, const char **))(*(_QWORD *)v53 + 32LL))(v53, &v58, &v55);
    }
    if ( (unsigned int)dword_1800C1058 > 5 )
    {
      if ( v55 )
      {
        v28 = *(_DWORD *)v55;
        v29 = -1;
      }
      else
      {
        v29 = -1;
        v28 = -1;
      }
      *(_DWORD *)v51 = v28;
      if ( *(_QWORD *)v56 )
        v30 = **(_DWORD **)v56;
      else
        v30 = -1;
      v50 = v30;
      if ( v57[0] )
        v29 = *(_DWORD *)v57[0];
      v49 = v29;
      if ( v54 )
        v31 = *(_DWORD *)v54;
      else
        v31 = 0;
      v59 = v31;
      if ( v54 )
        v32 = *((_DWORD *)v54 + 1);
      else
        v32 = 0;
      v60 = v32;
      v33 = "NV12";
      v34 = "NV12";
      if ( *((_DWORD *)this + 52) != 103 )
        v34 = "BGRA";
      if ( DxgiFormatFromStreamFormat != 103 )
        v33 = "BGRA";
      v35 = *((_QWORD *)this + 17);
      v61 = *(_DWORD *)(*(_QWORD *)(v35 + 104) + 136LL);
      v62 = *(_DWORD *)(v35 + 128);
      v52 = 371;
      v95 = v51;
      v96 = 4;
      v93 = &v50;
      v94 = 4;
      v91 = &v49;
      v92 = 4;
      v89 = &v59;
      v90 = 4;
      v87 = &v60;
      v88 = 4;
      v36 = -1;
      do
        ++v36;
      while ( v34[v36] );
      v84 = v34;
      v85 = v36 + 1;
      v86 = 0;
      v37 = -1;
      do
        ++v37;
      while ( v33[v37] );
      v81 = v33;
      v82 = v37 + 1;
      v83 = 0;
      v79 = v35 + 112;
      v80 = 16;
      v77 = &v61;
      v78 = 4;
      v75 = &v62;
      v76 = 4;
      v73 = "SessionFormat";
      v74 = 14;
      v71 = "Rdp::Avenc::Ic3::CDsStreamSource::Start";
      v72 = 40;
      v69 = &v52;
      v70 = 4;
      v67 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\dsstreamsource.cpp";
      v68 = 72;
      tlgWriteTransfer_EventWriteTransfer(
        (__int64)&dword_1800C1058,
        (unsigned __int8 *)word_1800B28F2,
        0,
        0,
        0x10u,
        &v66);
    }
    if ( *((_DWORD *)this + 52) != DxgiFormatFromStreamFormat )
    {
      *((_DWORD *)this + 52) = DxgiFormatFromStreamFormat;
      v38 = *((_QWORD *)this + 17);
      if ( *(_QWORD *)(v38 + 216) )
      {
        Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::IGpuFrameProcessor,Rdp::Avenc::IGpuFrameAsyncProcessor>::OnVideoFormatChanged(*(_QWORD *)(v38 + 216));
      }
      else if ( *(_QWORD *)(v38 + 224) )
      {
        Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::ICpuFrameProcessor,Rdp::Avenc::ICpuFrameAsyncProcessor>::OnVideoFormatChanged();
      }
    }
    if ( v53 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
    _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
      (void **)this + 30,
      1);
    if ( v63[0] )
      (*(void (__fastcall **)(struct ds::nanocom::IStreamProcessingSession::ICallback *))(*(_QWORD *)v63[0] + 16LL))(v63[0]);
    if ( (*((_DWORD *)this + 31))-- == 1 )
    {
      *((_DWORD *)this + 30) = -1;
      ReleaseSRWLockExclusive((PSRWLOCK)this + 8);
    }
    EventActivityIdControl(2u, &ActivityId);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x180,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\dsstreamsource.cpp",
                           v40);
  }
  return result;
}

```

## disassembly

```asm
0x180050c50  push    rbx
0x180050c52  push    rsi
0x180050c53  push    rdi
0x180050c54  push    r12
0x180050c56  push    r13
0x180050c58  push    r14
0x180050c5a  push    r15
0x180050c5c  sub     rsp, 200h
0x180050c63  mov     rax, cs:__security_cookie
0x180050c6a  xor     rax, rsp
0x180050c6d  mov     [rsp+238h+var_48], rax
0x180050c75  mov     r12, r8
0x180050c78  mov     r15, rdx
0x180050c7b  mov     rbx, rcx
0x180050c7e  movups  xmm0, cs:xmmword_1800C21A0
0x180050c85  movdqu  xmmword ptr [rsp+238h+ActivityId.Data1], xmm0
0x180050c8e  lea     rdx, [rsp+238h+ActivityId]; ActivityId
0x180050c96  mov     ecx, 4; ControlCode
0x180050c9b  call    cs:__imp_EventActivityIdControl
0x180050ca1  nop
0x180050ca2  mov     rcx, [rsp+238h]; this
0x180050caa  test    r15, r15
0x180050cad  jz      loc_180051444
0x180050cb3  mov     rcx, [rsp+238h]; this
0x180050cbb  test    r12, r12
0x180050cbe  jz      loc_18005145B
0x180050cc4  cmp     qword ptr [rbx+0D8h], 0
0x180050ccc  setnz   al
0x180050ccf  mov     rcx, [rsp+238h]; this
0x180050cd7  lea     rdx, aStreamSourceIs; "Stream source is already started"
0x180050cde  mov     [rsp+238h+var_210], rdx; bool
0x180050ce3  mov     byte ptr [rsp+238h+var_218], al; int
0x180050ce7  mov     r9d, 8000FFFFh; char *
0x180050ced  lea     rdi, aOnecoreuapTerm_34; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180050cf4  mov     r8, rdi; unsigned int
0x180050cf7  mov     edx, 131h; void *
0x180050cfc  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180050d01  lea     rsi, [rbx+30h]
0x180050d05  mov     [rsp+238h+var_170], rsi
0x180050d0d  mov     [rsp+238h+var_168], 0
0x180050d15  mov     rcx, rsi
0x180050d18  call    mtx_do_lock
0x180050d1d  test    eax, eax
0x180050d1f  jnz     loc_180051472
0x180050d25  mov     eax, [rsi+4Ch]
0x180050d28  cmp     eax, 7FFFFFFFh
0x180050d2d  jz      loc_18005147C
0x180050d33  mov     [rsp+238h+var_168], 1
0x180050d3b  mov     eax, cs:dword_1800C1058
0x180050d41  cmp     eax, 5
0x180050d44  jbe     loc_180050E02
0x180050d4a  mov     rdx, [rbx+88h]
0x180050d51  lea     rax, [rdx+70h]
0x180050d55  mov     [rsp+238h+var_1C0], rax
0x180050d5a  mov     rax, [rdx+68h]
0x180050d5e  mov     ecx, [rax+88h]
0x180050d64  mov     [rsp+238h+var_1D8], ecx
0x180050d68  mov     eax, [rdx+80h]
0x180050d6e  mov     [rsp+238h+var_1D4], eax
0x180050d72  lea     rax, aStart; "Start"
0x180050d79  mov     [rsp+238h+var_1A8], rax
0x180050d81  lea     rax, aRdpAvencIc3Cds_5; "Rdp::Avenc::Ic3::CDsStreamSource::Start"
0x180050d88  mov     qword ptr [rsp+238h+var_1B0], rax
0x180050d90  mov     dword ptr [rsp+238h+var_1D0], 13Bh
0x180050d98  mov     [rsp+238h+var_1B8], rdi
0x180050da0  lea     rax, [rsp+238h+var_1C0]
0x180050da5  mov     [rsp+238h+var_1E8], rax
0x180050daa  lea     rax, [rsp+238h+var_1D8]
0x180050daf  mov     [rsp+238h+var_1F0], rax
0x180050db4  lea     rax, [rsp+238h+var_1D4]
0x180050db9  mov     [rsp+238h+var_1F8], rax
0x180050dbe  lea     rax, [rsp+238h+var_1A8]
0x180050dc6  mov     [rsp+238h+var_200], rax
0x180050dcb  lea     rax, [rsp+238h+var_1B0]
0x180050dd3  mov     [rsp+238h+var_208], rax; char *
0x180050dd8  lea     rax, [rsp+238h+var_1D0]
0x180050ddd  mov     [rsp+238h+var_210], rax; char *
0x180050de2  lea     rax, [rsp+238h+var_1B8]
0x180050dea  mov     qword ptr [rsp+238h+var_218], rax
0x180050def  lea     rdx, byte_1800B299D
0x180050df6  lea     rcx, dword_1800C1058
0x180050dfd  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x180050e02  mov     rax, [r15]
0x180050e05  mov     r13, [rax+20h]
0x180050e09  lea     r14, [rbx+98h]
0x180050e10  mov     rcx, [r14]
0x180050e13  mov     qword ptr [r14], 0
0x180050e1a  test    rcx, rcx
0x180050e1d  jz      short loc_180050E2C
0x180050e1f  mov     rdx, [rcx]
0x180050e22  mov     rax, [rdx+10h]
0x180050e26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050e2b  nop
0x180050e2c  mov     rdx, r14
0x180050e2f  mov     rcx, r15
0x180050e32  mov     rax, r13
0x180050e35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050e3a  mov     rcx, [rsp+238h]; this
0x180050e42  lea     rdx, aFailedToGetOut; "Failed to get output stream format from"...
0x180050e49  mov     qword ptr [rsp+238h+var_218], rdx; int
0x180050e4e  mov     r9d, eax; char *
0x180050e51  mov     r8, rdi; unsigned int
0x180050e54  mov     edx, 13Eh; void *
0x180050e59  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180050e5e  xor     r13d, r13d
0x180050e61  cmp     [r14], r13
0x180050e64  setz    al
0x180050e67  mov     rcx, [rsp+238h]; this
0x180050e6f  lea     rdx, aFailedToGetNon; "Failed to get non-nullptr output stream"...
0x180050e76  mov     [rsp+238h+var_210], rdx; char *
0x180050e7b  mov     byte ptr [rsp+238h+var_218], al; int
0x180050e7f  mov     r9d, 8000FFFFh; char *
0x180050e85  mov     r8, rdi; unsigned int
0x180050e88  mov     edx, 13Fh; void *
0x180050e8d  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180050e92  nop
0x180050e93  mov     rax, [r15]
0x180050e96  mov     [rsp+238h+var_178], r13
0x180050e9e  lea     rdx, [rsp+238h+var_178]
0x180050ea6  mov     rcx, r15
0x180050ea9  mov     rax, [rax+28h]
0x180050ead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050eb2  mov     rcx, [rsp+238h]; this
0x180050eba  lea     rdx, aFailedToGetCal; "Failed to get callback from stream proc"...
0x180050ec1  mov     qword ptr [rsp+238h+var_218], rdx; int
0x180050ec6  mov     r9d, eax; char *
0x180050ec9  mov     r8, rdi; unsigned int
0x180050ecc  mov     edx, 143h; void *
0x180050ed1  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180050ed6  mov     ecx, 0F8h; Size
0x180050edb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180050ee0  mov     [rsp+238h+var_1C0], rax
0x180050ee5  mov     r9, [rsp+238h+var_178]; struct ds::nanocom::IStreamProcessingSession::ICallback *
0x180050eed  mov     r8, [r14]; struct ds::nanocom::IStreamFormat *
0x180050ef0  mov     rdx, [rbx+88h]; struct Rdp::Avenc::Ic3::CMonitorContext *
0x180050ef7  mov     rcx, rax; this
0x180050efa  call    ??0CDsSourceStreamProcessingSession@Ic3@Avenc@Rdp@@QEAA@PEAVCMonitorContext@123@PEAUIStreamFormat@nanocom@ds@@PEAUICallback@IStreamProcessingSession@67@@Z; Rdp::Avenc::Ic3::CDsSourceStreamProcessingSession::CDsSourceStreamProcessingSession(Rdp::Avenc::Ic3::CMonitorContext *,ds::nanocom::IStreamFormat *,ds::nanocom::IStreamProcessingSession::ICallback *)
0x180050eff  nop
0x180050f00  mov     r15, [rbx+0D8h]
0x180050f07  mov     [rbx+0D8h], rax
0x180050f0e  test    rax, rax
0x180050f11  jz      short loc_180050F2E
0x180050f13  mov     rcx, [rax+8]
0x180050f17  movsxd  rcx, dword ptr [rcx+4]
0x180050f1b  add     rax, 8
0x180050f1f  add     rcx, rax
0x180050f22  mov     rax, [rcx]
0x180050f25  mov     rax, [rax+8]
0x180050f29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050f2e  test    r15, r15
0x180050f31  jz      short loc_180050F4E
0x180050f33  mov     rax, [r15+8]
0x180050f37  movsxd  rcx, dword ptr [rax+4]
0x180050f3b  add     rcx, 8
0x180050f3f  add     rcx, r15
0x180050f42  mov     rax, [rcx]
0x180050f45  mov     rax, [rax+10h]
0x180050f49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050f4e  mov     rdx, [rbx+80h]; struct ID3D11Device *
0x180050f55  test    rdx, rdx
0x180050f58  jz      short loc_180050F76
0x180050f5a  mov     rcx, [rbx+0D8h]; this
0x180050f61  call    ?SetEncodeDevice@CDsSourceStreamProcessingSession@Ic3@Avenc@Rdp@@QEAAJPEAUID3D11Device@@@Z; Rdp::Avenc::Ic3::CDsSourceStreamProcessingSession::SetEncodeDevice(ID3D11Device *)
0x180050f66  mov     rcx, [rsp+238h]; this
0x180050f6e  test    eax, eax
0x180050f70  js      loc_18005148C
0x180050f76  mov     rdx, [rbx+0D8h]
0x180050f7d  test    rdx, rdx
0x180050f80  jz      short loc_180050FB8
0x180050f82  mov     rax, [rdx+8]
0x180050f86  movsxd  rcx, dword ptr [rax+4]
0x180050f8a  add     rdx, 8
0x180050f8e  add     rcx, rdx
0x180050f91  mov     rax, [rcx]
0x180050f94  mov     r8, r12
0x180050f97  lea     rdx, _GUID_e6567424_d3ae_5566_6f43_31760af27908
0x180050f9e  mov     rax, [rax]
0x180050fa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050fa6  mov     rcx, [rsp+238h]; this
0x180050fae  test    eax, eax
0x180050fb0  js      loc_18005149C
0x180050fb6  jmp     short loc_180050FBC
0x180050fb8  mov     [r12], r13
0x180050fbc  mov     rcx, [r14]
0x180050fbf  call    _anonymous_namespace___GetDxgiFormatFromStreamFormat
0x180050fc4  mov     r15d, eax
0x180050fc7  mov     [rsp+238h+var_1C8], r13
0x180050fcc  mov     rcx, [r14]
0x180050fcf  mov     rdx, [rcx]
0x180050fd2  mov     rax, [rdx+28h]
0x180050fd6  mov     [rsp+238h+var_1C8], r13
0x180050fdb  movups  xmm0, cs:xmmword_18009A2D0
0x180050fe2  movdqu  [rsp+238h+var_198], xmm0
0x180050feb  lea     r8, [rsp+238h+var_1C8]
0x180050ff0  lea     rdx, [rsp+238h+var_198]
0x180050ff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050ffd  mov     [rsp+238h+var_1A8], r13
0x180051005  mov     qword ptr [rsp+238h+var_1B0], r13
0x18005100d  mov     [rsp+238h+var_1B8], r13
0x180051015  mov     [rsp+238h+var_1C0], r13
0x18005101a  test    eax, eax
0x18005101c  js      loc_1800510EC
0x180051022  mov     rcx, [rsp+238h+var_1C8]
0x180051027  test    rcx, rcx
0x18005102a  jz      loc_1800510EC
0x180051030  movups  xmm0, cs:xmmword_18009A250
0x180051037  movdqu  [rsp+238h+var_198], xmm0
0x180051040  mov     rax, [rcx]
0x180051043  lea     r8, [rsp+238h+var_1C0]
0x180051048  lea     rdx, [rsp+238h+var_198]
0x180051050  mov     rax, [rax+20h]
0x180051054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051059  mov     rcx, [rsp+238h+var_1C8]
0x18005105e  movups  xmm0, cs:xmmword_18009A2B8
0x180051065  movdqu  [rsp+238h+var_198], xmm0
0x18005106e  mov     rax, [rcx]
0x180051071  lea     r8, [rsp+238h+var_1A8]
0x180051079  lea     rdx, [rsp+238h+var_198]
0x180051081  mov     rax, [rax+20h]
0x180051085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005108a  mov     rcx, [rsp+238h+var_1C8]
0x18005108f  movups  xmm0, cs:xmmword_18009A260
0x180051096  movdqu  [rsp+238h+var_198], xmm0
0x18005109f  mov     rax, [rcx]
0x1800510a2  lea     r8, [rsp+238h+var_1B0]
0x1800510aa  lea     rdx, [rsp+238h+var_198]
0x1800510b2  mov     rax, [rax+20h]
0x1800510b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800510bb  mov     rcx, [rsp+238h+var_1C8]
0x1800510c0  movups  xmm0, cs:xmmword_18009A240
0x1800510c7  movdqu  [rsp+238h+var_198], xmm0
0x1800510d0  mov     rax, [rcx]
0x1800510d3  lea     r8, [rsp+238h+var_1B8]
0x1800510db  lea     rdx, [rsp+238h+var_198]
0x1800510e3  mov     rax, [rax+20h]
0x1800510e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800510ec  mov     eax, cs:dword_1800C1058
0x1800510f2  cmp     eax, 5
0x1800510f5  jbe     loc_18005136C
0x1800510fb  mov     rax, [rsp+238h+var_1B8]
0x180051103  test    rax, rax
0x180051106  jz      short loc_18005110F
0x180051108  mov     ecx, [rax]
0x18005110a  or      eax, 0FFFFFFFFh
0x18005110d  jmp     short loc_180051114
0x18005110f  or      eax, 0FFFFFFFFh
0x180051112  mov     ecx, eax
0x180051114  mov     dword ptr [rsp+238h+var_1D0], ecx
0x180051118  mov     rcx, qword ptr [rsp+238h+var_1B0]
0x180051120  test    rcx, rcx
0x180051123  jz      short loc_180051129
0x180051125  mov     ecx, [rcx]
0x180051127  jmp     short loc_18005112B
0x180051129  mov     ecx, eax
0x18005112b  mov     [rsp+238h+var_1D4], ecx
0x18005112f  mov     rcx, [rsp+238h+var_1A8]
0x180051137  test    rcx, rcx
0x18005113a  jz      short loc_18005113E
0x18005113c  mov     eax, [rcx]
0x18005113e  mov     [rsp+238h+var_1D8], eax
0x180051142  mov     rax, [rsp+238h+var_1C0]
0x180051147  test    rax, rax
0x18005114a  jz      short loc_180051150
0x18005114c  mov     ecx, [rax]
0x18005114e  jmp     short loc_180051153
0x180051150  mov     ecx, r13d
0x180051153  mov     [rsp+238h+var_188], ecx
0x18005115a  test    rax, rax
0x18005115d  jz      short loc_180051164
0x18005115f  mov     ecx, [rax+4]
0x180051162  jmp     short loc_180051167
0x180051164  mov     ecx, r13d
0x180051167  mov     [rsp+238h+var_184], ecx
0x18005116e  lea     rax, aBgra; "BGRA"
0x180051175  lea     r8, aNv12; "NV12"
0x18005117c  mov     r9, r8
0x18005117f  cmp     dword ptr [rbx+0D0h], 67h ; 'g'
0x180051186  cmovnz  r9, rax
0x18005118a  cmp     r15d, 67h ; 'g'
0x18005118e  cmovnz  r8, rax
0x180051192  mov     rdx, [rbx+88h]
0x180051199  lea     r10, [rdx+70h]
0x18005119d  mov     rax, [rdx+68h]
0x1800511a1  mov     ecx, [rax+88h]
0x1800511a7  mov     [rsp+238h+var_180], ecx
0x1800511ae  mov     eax, [rdx+80h]
0x1800511b4  mov     [rsp+238h+var_17C], eax
0x1800511bb  mov     [rsp+238h+var_1CC], 173h
0x1800511c3  lea     rax, [rsp+238h+var_1D0]
0x1800511c8  mov     [rsp+238h+var_58], rax
0x1800511d0  mov     [rsp+238h+var_50], 4
0x1800511dc  lea     rax, [rsp+238h+var_1D4]
0x1800511e1  mov     [rsp+238h+var_68], rax
0x1800511e9  mov     [rsp+238h+var_60], 4
0x1800511f5  lea     rax, [rsp+238h+var_1D8]
0x1800511fa  mov     [rsp+238h+var_78], rax
0x180051202  mov     [rsp+238h+var_70], 4
0x18005120e  lea     rax, [rsp+238h+var_188]
0x180051216  mov     [rsp+238h+var_88], rax
0x18005121e  mov     [rsp+238h+var_80], 4
  ... truncated ...
```
