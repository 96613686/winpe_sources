# Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::ICpuFrameProcessor,Rdp::Avenc::ICpuFrameAsyncProcessor>::ProcessFrameInternal<Rdp::Avenc::IFrameSystemBuffer1>(Rdp::Avenc::IFrameSystemBuffer1 *)

- ea: `0x180046944`
- end: `0x180047abc`
- name: `??$ProcessFrameInternal@UIFrameSystemBuffer1@Avenc@Rdp@@@?$CIc3FrameProcessor@UICpuFrameProcessor@Avenc@Rdp@@UICpuFrameAsyncProcessor@23@@Ic3@Avenc@Rdp@@IEAAJPEAUIFrameSystemBuffer1@23@@Z`
- size: `4472`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x180044720`

## callees

- `0x180001f30`
- `0x180004660`
- `0x18000490c`
- `0x180004a44`
- `0x180004cd4`
- `0x180004e20`
- `0x1800065a4`
- `0x18000e848`
- `0x18000ec04`
- `0x1800103c0`
- `0x180010bc8`
- `0x1800203d4`
- `0x1800455f0`
- `0x180046944`
- `0x180047ca4`
- `0x180048f2c`
- `0x18004936c`
- `0x18004f6f4`
- `0x180054820`
- `0x18005842c`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004718d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004718d`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180046e19`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x18004746b`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180046e19`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x18004746b`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x180046e4f`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x1800474a1`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x180046e4f`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x1800474a1`

## string_xrefs

- `0x180047aa9`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180046b5d`: `Failed to get moves and dirties`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
__int64 __fastcall Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::ICpuFrameProcessor,Rdp::Avenc::ICpuFrameAsyncProcessor>::ProcessFrameInternal<Rdp::Avenc::IFrameSystemBuffer1>(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rdi
  __int64 v4; // rbx
  __int64 v5; // r12
  int v6; // r14d
  int v7; // r15d
  int v8; // r8d
  int v9; // r9d
  unsigned int v10; // r14d
  __int64 v11; // rbx
  const char *v12; // r9
  __int64 v13; // rcx
  __int64 v14; // r15
  const char *v15; // r15
  __int64 v16; // r14
  int v17; // ebx
  __int64 v18; // r9
  __int64 v19; // rax
  int v20; // r8d
  struct Rdp::Avenc::Ic3::CDsStreamSample *v21; // rbx
  __int64 v22; // rcx
  int v23; // r8d
  int v24; // r9d
  __int64 v25; // r14
  char *v26; // rcx
  __int64 v27; // rcx
  Rdp::Avenc::Ic3::CDsSourceStreamProcessingSession *v28; // r14
  char *v29; // rcx
  __int64 v30; // rax
  int v31; // r8d
  int v32; // r9d
  int v33; // r8d
  int v34; // r9d
  bool v35; // r15
  __int64 v36; // rax
  __int64 v37; // r8
  char *v38; // rcx
  __int64 v39; // rcx
  Rdp::Avenc::Ic3::CVideoSourceProvider *v41; // rcx
  Rdp::Avenc::Ic3::CDsSourceStreamProcessingSession *v42; // r14
  __int64 v43; // rbx
  __int64 (__fastcall ***v44)(_QWORD, GUID *, const char **); // rax
  int v45; // eax
  void (__fastcall ***v46)(_QWORD); // rax
  int v47; // r8d
  _QWORD *v48; // rbx
  __int64 v49; // r14
  __int64 v50; // r14
  __int64 v51; // rax
  int v52; // r8d
  int v53; // r9d
  int v54; // r8d
  int v55; // r9d
  int v56; // r8d
  int v57; // r9d
  __int64 v58; // rax
  __int64 v59; // r8
  int v60; // esi
  int v61; // r8d
  int v62; // r9d
  wil *v64; // rcx
  int v65; // r13d
  int v66; // eax
  __int64 v67; // rcx
  int v68; // [rsp+20h] [rbp-138h]
  char *v69; // [rsp+28h] [rbp-130h]
  char *v70; // [rsp+28h] [rbp-130h]
  char *v71; // [rsp+28h] [rbp-130h]
  const char *v72; // [rsp+90h] [rbp-C8h] BYREF
  const char *v73; // [rsp+98h] [rbp-C0h] BYREF
  const char *v74; // [rsp+A0h] [rbp-B8h] BYREF
  int v75; // [rsp+A8h] [rbp-B0h]
  int v76; // [rsp+ACh] [rbp-ACh]
  const char *v77; // [rsp+B0h] [rbp-A8h] BYREF
  const char *v78; // [rsp+B8h] [rbp-A0h] BYREF
  const char *v79; // [rsp+C0h] [rbp-98h] BYREF
  struct IVirtualVideoSink *Sink; // [rsp+C8h] [rbp-90h] BYREF
  const char *v81; // [rsp+D0h] [rbp-88h] BYREF
  const char *v82; // [rsp+D8h] [rbp-80h] BYREF
  int v83; // [rsp+E0h] [rbp-78h] BYREF
  const char *v84; // [rsp+E8h] [rbp-70h] BYREF
  __int64 v85; // [rsp+F0h] [rbp-68h] BYREF
  __int64 *v86; // [rsp+F8h] [rbp-60h]
  Rdp::Avenc::Ic3::CDsSourceStreamProcessingSession *v87; // [rsp+100h] [rbp-58h]
  __int64 v88; // [rsp+108h] [rbp-50h]
  char v89; // [rsp+110h] [rbp-48h]
  __int64 v90; // [rsp+118h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+0h]
  __int64 v92; // [rsp+160h] [rbp+8h] BYREF
  __int64 v93; // [rsp+168h] [rbp+10h]
  __int64 v94; // [rsp+170h] [rbp+18h] BYREF
  int v95; // [rsp+178h] [rbp+20h] BYREF

  v93 = a2;
  v92 = a1;
  v2 = a2;
  LODWORD(v94) = 0;
  v4 = a1 + 176;
  v86 = (__int64 *)(a1 + 176);
  v5 = *(_QWORD *)(*(_QWORD *)(a1 + 176) + 104LL);
  v85 = v5;
  v90 = v5;
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
  try
  {
    v6 = *(_DWORD *)(v5 + 136);
    v75 = v6;
    v7 = *(_DWORD *)(*(_QWORD *)v4 + 128LL);
    v76 = v7;
    if ( (unsigned int)dword_1800C1058 > 5 )
    {
      v79 = (const char *)(*(_QWORD *)v4 + 112LL);
      v73 = (const char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 200LL))(v2);
      LODWORD(v94) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 192LL))(v2);
      v95 = v6;
      LODWORD(v81) = v7;
      v74 = "NewFrame";
      v77 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::ICpuFrameProcessor,struct Rdp::Avenc::ICpuFrameAsyncP"
            "rocessor>::ProcessFrameInternal";
      LODWORD(Sink) = 810;
      v72 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)&unk_1800B1CF8,
        v8,
        v9,
        (__int64)&v72,
        (__int64)&Sink,
        (__int64)&v77,
        (__int64)&v74,
        (__int64)&v81,
        (__int64)&v95,
        (__int64)&v94,
        (__int64)&v73,
        (__int64)&v79);
    }
    v83 = 0;
    v84 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 40LL))(v2);
    v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, const char **, int *))(*(_QWORD *)v2 + 208LL))(
            v2,
            0,
            0,
            &v84,
            &v83);
    v95 = v10;
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x33D,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
      (const char *)v10,
      (int)"Failed to get moves and dirties",
      v69);
    v11 = a1 + 256;
    v88 = a1 + 256;
    v89 = 0;
    if ( (unsigned int)mtx_do_lock(a1 + 256) )
      std::_Throw_Cpp_error(5);
    if ( *(_DWORD *)(a1 + 332) == 0x7FFFFFFF )
    {
      *(_DWORD *)(a1 + 332) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    v89 = 1;
    if ( *(_QWORD *)(a1 + 208) )
    {
      v13 = *(_QWORD *)(a1 + 232);
      if ( v13 && (v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 24LL))(v13)) != 0 )
        v15 = (const char *)(v14
                           - anonymous_namespace_::GetTimePassedSinceAcquisition_Rdp::Avenc::IFrameSystemBuffer1_(v2));
      else
        v15 = (const char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 200LL))(v2);
      v72 = (const char *)operator new(0xA8u);
      v82 = v72;
      if ( *(_BYTE *)(*v86 + 288) )
        v16 = 0;
      else
        v16 = *v86;
      v17 = *(_DWORD *)(*v86 + 128);
      v79 = (const char *)v2;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
      LODWORD(v94) = 1;
      v19 = Rdp::Avenc::Ic3::CDsStreamSample::CDsStreamSample((__int64)v72, &v79, v17, v18, a1 + 448, v16, (__int64)v15);
      v21 = (struct Rdp::Avenc::Ic3::CDsStreamSample *)v19;
      v82 = (const char *)v19;
      if ( v19 )
      {
        v22 = v19 + *(int *)(*(_QWORD *)(v19 + 8) + 4LL) + 8LL;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 8LL))(v22);
      }
      if ( v79 )
        (*(void (__fastcall **)(const char *))(*(_QWORD *)v79 + 16LL))(v79);
      if ( (unsigned int)dword_1800C1058 > 5 )
      {
        v72 = v15;
        v77 = (const char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 200LL))(v2);
        v79 = "Match";
        v73 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::ICpuFrameProcessor,struct Rdp::Avenc::ICpuFrameAsyn"
              "cProcessor>::ProcessFrameInternal";
        LODWORD(v94) = 857;
        v74 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_1800C1058,
          (unsigned int)&dword_1800B1BAC,
          v23,
          v24,
          (__int64)&v74,
          (__int64)&v94,
          (__int64)&v73,
          (__int64)&v79,
          (__int64)&v77,
          (__int64)&v72);
      }
      if ( *(_BYTE *)(v5 + 288) )
      {
        v25 = *(_QWORD *)(a1 + 240);
        *(_QWORD *)(a1 + 240) = v21;
        if ( v21 )
        {
          v26 = (char *)v21 + *(int *)(*((_QWORD *)v21 + 1) + 4LL) + 8;
          (*(void (__fastcall **)(char *))(*(_QWORD *)v26 + 8LL))(v26);
        }
        if ( v25 )
        {
          v27 = v25 + *(int *)(*(_QWORD *)(v25 + 8) + 4LL) + 8LL;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
        }
        v94 = 0;
        GetSystemTimePreciseAsFileTime(&v94);
        *(_QWORD *)(a1 + 424) = ((unsigned __int64)HIDWORD(v94) << 32) - 116444736000000000LL + (unsigned int)v94;
        WakeConditionVariable((PCONDITION_VARIABLE)(a1 + 344));
      }
      v28 = *(Rdp::Avenc::Ic3::CDsSourceStreamProcessingSession **)(*(_QWORD *)(a1 + 208) + 280LL);
      v87 = v28;
      if ( v28 )
      {
        v29 = (char *)v28 + *(int *)(*((_QWORD *)v28 + 1) + 4LL) + 8;
        (*(void (__fastcall **)(char *))(*(_QWORD *)v29 + 8LL))(v29);
        v30 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 200LL))(v2);
        LOBYTE(v94) = Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::ICpuFrameProcessor,Rdp::Avenc::ICpuFrameAsyncProcessor>::CheckFirstFrameAndRaiseEvent(
                        a1,
                        v30,
                        v15);
        if ( (unsigned int)dword_1800C1058 > 5 )
        {
          v72 = (const char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 200LL))(v2);
          v95 = v75;
          LODWORD(Sink) = v76;
          v77 = "Start";
          v79 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::ICpuFrameProcessor,struct Rdp::Avenc::ICpuFrameAs"
                "yncProcessor>::ProcessFrameInternal";
          LODWORD(v81) = 877;
          v73 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
            (unsigned int)&dword_1800C1058,
            (unsigned int)byte_1800B1C15,
            v31,
            v32,
            (__int64)&v73,
            (__int64)&v81,
            (__int64)&v79,
            (__int64)&v77,
            (__int64)&Sink,
            (__int64)&v95,
            (__int64)&v72);
        }
        v95 = Rdp::Avenc::Ic3::CDsSourceStreamProcessingSession::ProcessFrame(v28, v21);
        wil::details::in1diag3::Log_IfFailedMsg(
          retaddr,
          (void *)0x370,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
          (const char *)(unsigned int)v95,
          (int)"ProcessFrame failed",
          v70);
        if ( (unsigned int)dword_1800C1058 > 5 )
        {
          LODWORD(Sink) = v95 == 0;
          v72 = (const char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 200LL))(v2);
          LODWORD(v81) = v75;
          LODWORD(v74) = v76;
          v77 = "End";
          v79 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::ICpuFrameProcessor,struct Rdp::Avenc::ICpuFrameAs"
                "yncProcessor>::ProcessFrameInternal";
          LODWORD(v73) = 889;
          v78 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_1800C1058,
            (unsigned int)&unk_1800B1AE0,
            v33,
            v34,
            (__int64)&v78,
            (__int64)&v73,
            (__int64)&v79,
            (__int64)&v77,
            (__int64)&v74,
            (__int64)&v81,
            (__int64)&v72,
            (__int64)&Sink);
        }
        if ( (_BYTE)v94 )
        {
          v35 = v95 >= 0;
          v36 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 200LL))(v2);
          LOBYTE(v37) = v35;
          Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::ICpuFrameProcessor,Rdp::Avenc::ICpuFrameAsyncProcessor>::RaiseFirstFrameDoneEvent(
            a1,
            v36,
            v37);
        }
      }
      else if ( !*(_BYTE *)(a1 + 200) )
      {
        if ( (unsigned int)dword_1800C1058 > 5 )
        {
          LODWORD(v94) = v75;
          LODWORD(v73) = v76;
          v78 = "Stream processing session stopped";
          v72 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::ICpuFrameProcessor,struct Rdp::Avenc::ICpuFrameAs"
                "yncProcessor>::ProcessFrameInternal";
          LODWORD(v74) = 905;
          v77 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_1800C1058,
            (unsigned int)&byte_1800B1B57,
            v20,
            (_DWORD)v12,
            (__int64)&v77,
            (__int64)&v74,
            (__int64)&v72,
            (__int64)&v78,
            (__int64)&v73,
            (__int64)&v94);
        }
        *(_BYTE *)(a1 + 200) = 1;
      }
      if ( v28 )
      {
        v38 = (char *)v28 + *(int *)(*((_QWORD *)v28 + 1) + 4LL) + 8;
        (*(void (__fastcall **)(char *))(*(_QWORD *)v38 + 16LL))(v38);
      }
      if ( v21 )
      {
        v39 = (__int64)v21 + *(int *)(*((_QWORD *)v21 + 1) + 4LL) + 8;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
      }
      v10 = v95;
LABEL_39:
      v11 = v88;
      goto LABEL_40;
    }
    v41 = *(Rdp::Avenc::Ic3::CVideoSourceProvider **)(a1 + 216);
    if ( !v41 )
    {
LABEL_40:
      if ( (*(_DWORD *)(v11 + 76))-- == 1 )
      {
        *(_DWORD *)(v11 + 72) = -1;
        ReleaseSRWLockExclusive((PSRWLOCK)(v11 + 16));
      }
      goto LABEL_90;
    }
    Sink = Rdp::Avenc::Ic3::CVideoSourceProvider::GetSink(v41);
    v42 = (Rdp::Avenc::Ic3::CDsSourceStreamProcessingSession *)operator new(0xD0u);
    v87 = v42;
    v78 = (const char *)anonymous_namespace_::GetTimePassedSinceAcquisition_Rdp::Avenc::IFrameSystemBuffer1_(v2);
    if ( *(_BYTE *)(*(_QWORD *)(a1 + 176) + 288LL) )
      v43 = 0;
    else
      v43 = *(_QWORD *)(a1 + 176);
    LODWORD(v73) = *(_DWORD *)(*(_QWORD *)(a1 + 176) + 128LL);
    v74 = (const char *)v2;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
    LODWORD(v94) = 2;
    v44 = (__int64 (__fastcall ***)(_QWORD, GUID *, const char **))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 216LL))(v2);
    v79 = 0;
    v45 = (**v44)(v44, &GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c, &v79);
    if ( v45 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v45,
        v68);
    LODWORD(v94) = 14;
    v46 = (void (__fastcall ***)(_QWORD))Rdp::Avenc::Ic3::CVirtualFrame::CVirtualFrame(
                                           (__int64)v42,
                                           (__int64 *)&v79,
                                           a1 + 448,
                                           &v74,
                                           v68,
                                           SLODWORD(FLOAT_60_0),
                                           (unsigned int)v73,
                                           v43,
                                           (__int64)v78);
    v48 = v46;
    v87 = (Rdp::Avenc::Ic3::CDsSourceStreamProcessingSession *)v46;
    if ( v46 )
      (**v46)(v46);
    LODWORD(v94) = 10;
    if ( v79 )
      (*(void (__fastcall **)(const char *))(*(_QWORD *)v79 + 16LL))(v79);
    if ( v74 )
      (*(void (__fastcall **)(const char *))(*(_QWORD *)v74 + 16LL))(v74);
    if ( *(_BYTE *)(v5 + 288) )
    {
      v49 = *(_QWORD *)(a1 + 248);
      *(_QWORD *)(a1 + 248) = v48;
      if ( v48 )
        (*(void (__fastcall **)(_QWORD *))*v48)(v48);
      if ( v49 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 8LL))(v49);
      v94 = 0;
      GetSystemTimePreciseAsFileTime(&v94);
      *(_QWORD *)(a1 + 424) = ((unsigned __int64)HIDWORD(v94) << 32) - 116444736000000000LL + (unsigned int)v94;
      WakeConditionVariable((PCONDITION_VARIABLE)(a1 + 344));
    }
    if ( Sink )
    {
      v48[24] = (*(__int64 (__fastcall **)(struct IVirtualVideoSink *))(*(_QWORD *)Sink + 16LL))(Sink) - v48[25];
      v50 = (*(__int64 (__fastcall **)(_QWORD *))(*v48 + 64LL))(v48);
      v51 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 200LL))(v2);
      LOBYTE(v94) = Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::ICpuFrameProcessor,Rdp::Avenc::ICpuFrameAsyncProcessor>::CheckFirstFrameAndRaiseEvent(
                      a1,
                      v51,
                      v50);
      if ( (unsigned int)dword_1800C1058 > 5 )
      {
        v78 = (const char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 200LL))(v2);
        v95 = v75;
        LODWORD(v73) = v76;
        v72 = "Start";
        v77 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::ICpuFrameProcessor,struct Rdp::Avenc::ICpuFrameAsyn"
              "cProcessor>::ProcessFrameInternal";
        LODWORD(v74) = 950;
        v81 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_1800C1058,
          (unsigned int)byte_1800B1A0D,
          v52,
          v53,
          (__int64)&v81,
          (__int64)&v74,
          (__int64)&v77,
          (__int64)&v72,
          (__int64)&v73,
          (__int64)&v95,
          (__int64)&v78);
      }
      if ( (unsigned int)dword_1800C1058 > 5 )
      {
        v78 = (const char *)(*(__int64 (__fastcall **)(_QWORD *))(*v48 + 64LL))(v48);
        v72 = (const char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 200LL))(v2);
        v77 = "Match";
        v73 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::ICpuFrameProcessor,struct Rdp::Avenc::ICpuFrameAsyn"
              "cProcessor>::ProcessFrameInternal";
        v95 = 957;
        v74 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_1800C1058,
          (unsigned int)&byte_1800B1A77,
          v54,
          v55,
          (__int64)&v74,
          (__int64)&v95,
          (__int64)&v73,
          (__int64)&v77,
          (__int64)&v72,
          (__int64)&v78);
      }
      v10 = (*(__int64 (__fastcall **)(struct IVirtualVideoSink *, _QWORD *))(*(_QWORD *)Sink + 128LL))(Sink, v48);
      v95 = v10;
      wil::details::in1diag3::Log_IfFailedMsg(
        retaddr,
        (void *)0x3C1,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
        (const char *)v10,
        (int)"DeliverFrame failed",
        v71);
      if ( (unsigned int)dword_1800C1058 > 5 )
      {
        LODWORD(v73) = v10 == 0;
        v78 = (const char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 200LL))(v2);
        LODWORD(v74) = v75;
        LODWORD(Sink) = v76;
        v72 = "End";
        v77 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::ICpuFrameProcessor,struct Rdp::Avenc::ICpuFrameAsyn"
              "cProcessor>::ProcessFrameInternal";
        LODWORD(v81) = 970;
        v82 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1800C1058,
          (unsigned int)byte_1800B1941,
          v56,
          v57,
          (__int64)&v82,
          (__int64)&v81,
          (__int64)&v77,
          (__int64)&v72,
          (__int64)&Sink,
          (__int64)&v74,
          (__int64)&v78,
          (__int64)&v73);
      }
      if ( !(_BYTE)v94 )
        goto LABEL_78;
      v58 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 200LL))(v2);
      LOBYTE(v59) = (v10 & 0x80000000) == 0;
      Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::ICpuFrameProcessor,Rdp::Avenc::ICpuFrameAsyncProcessor>::RaiseFirstFrameDoneEvent(
        a1,
        v58,
        v59);
    }
    else if ( !*(_BYTE *)(a1 + 200) )
    {
      if ( (unsigned int)dword_1800C1058 > 5 )
      {
        LODWORD(v94) = v75;
        LODWORD(v73) = v76;
        v82 = "Lost virtual video sink";
        v78 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::ICpuFrameProcessor,struct Rdp::Avenc::ICpuFrameAsyn"
              "cProcessor>::ProcessFrameInternal";
        LODWORD(v74) = 986;
        v72 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1800C1058,
          (unsigned int)&word_1800B19B6,
          v47,
          (_DWORD)v12,
          (__int64)&v72,
          (__int64)&v74,
          (__int64)&v78,
          (__int64)&v82,
          (__int64)&v73,
          (__int64)&v94);
      }
      *(_BYTE *)(a1 + 200) = 1;
    }
    v10 = v95;
LABEL_78:
    if ( v48 )
      (*(void (__fastcall **)(_QWORD *))(*v48 + 8LL))(v48);
    goto LABEL_39;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x3E5,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
      v12);
    v65 = wil::ResultFromCaughtException(v64);
    LODWORD(v94) = v65;
    v66 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v93 + 192LL))(v93);
    v67 = *(_QWORD *)(v92 + 176);
    Rdp::Modern::Utils::CInflightRecorder::pushN(
      (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      (wchar_t *)L"Frame dropped: Id {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}, FrameNumber: %d, Error: %#x",
      "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::ICpuFrameProcessor,struct Rdp::Avenc::ICpuFrameAsyncProcess"
      "or>::ProcessFrameInternal",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
      0x3EDu,
      *(_DWORD *)(v67 + 112),
      *(unsigned __int16 *)(v67 + 116),
      *(unsigned __int16 *)(v67 + 118),
      *(unsigned __int8 *)(v67 + 120),
      *(unsigned __int8 *)(v67 + 121),
      *(unsigned __int8 *)(v67 + 122),
      *(unsigned __int8 *)(v67 + 123),
      *(unsigned __int8 *)(v67 + 124),
      *(unsigned __int8 *)(v67 + 125),
      *(unsigned __int8 *)(v67 + 126),
      *(unsigned __int8 *)(v67 + 127),
      v66,
      v65);
    Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::ICpuFrameProcessor,Rdp::Avenc::ICpuFrameAsyncProcessor>::CompleteFrame<Rdp::Avenc::IFrameSystemBuffer1>(
      v92,
      v93);
    v2 = v93;
    v10 = v94;
    v5 = v85;
  }
LABEL_90:
  v60 = v75;
  if ( (unsigned int)dword_1800C1058 > 5 )
  {
    v85 = *v86 + 112;
    v82 = (const char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 200LL))(v2);
    LODWORD(v92) = v60;
    LODWORD(v94) = v76;
    v78 = "Finished";
    v84 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::ICpuFrameProcessor,struct Rdp::Avenc::ICpuFrameAsyncPro"
          "cessor>::ProcessFrameInternal";
    v95 = 1016;
    v72 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>>(
      (unsigned int)&dword_1800C1058,
      (unsigned int)word_1800B18CA,
      v61,
      v62,
      (__int64)&v72,
      (__int64)&v95,
      (__int64)&v84,
      (__int64)&v78,
      (__int64)&v94,
      (__int64)&v92,
      (__int64)&v82,
      (__int64)&v85);
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  return v10;
}

```

## disassembly

```asm
0x180046944  mov     r11, rsp
0x180046947  mov     [r11+10h], rdx
0x18004694b  mov     [r11+8], rcx
0x18004694f  push    rbx
0x180046950  push    rsi
0x180046951  push    rdi
0x180046952  push    r12
0x180046954  push    r13
0x180046956  push    r14
0x180046958  push    r15
0x18004695a  sub     rsp, 120h
0x180046961  mov     rdi, rdx
0x180046964  mov     rsi, rcx
0x180046967  mov     dword ptr [r11+18h], 0
0x18004696f  lea     rbx, [rcx+0B0h]
0x180046976  mov     [rsp+158h+var_60], rbx
0x18004697e  mov     rax, [rbx]
0x180046981  mov     r12, [rax+68h]
0x180046985  mov     [rsp+158h+var_68], r12
0x18004698d  mov     [r11-40h], r12
0x180046991  test    r12, r12
0x180046994  jz      short loc_1800469A7
0x180046996  mov     rax, [r12]
0x18004699a  mov     rcx, r12
0x18004699d  mov     rax, [rax+8]
0x1800469a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800469a6  nop
0x1800469a7  mov     r14d, [r12+88h]
0x1800469af  mov     [rsp+158h+var_B0], r14d
0x1800469b7  mov     rax, [rbx]
0x1800469ba  mov     r15d, [rax+80h]
0x1800469c1  mov     [rsp+158h+var_AC], r15d
0x1800469c9  mov     eax, cs:dword_1800C1058
0x1800469cf  mov     r13d, 5
0x1800469d5  cmp     eax, r13d
0x1800469d8  jbe     loc_180046AF2
0x1800469de  mov     rax, [rbx]
0x1800469e1  add     rax, 70h ; 'p'
0x1800469e5  mov     [rsp+158h+var_98], rax
0x1800469ed  mov     rax, [rdi]
0x1800469f0  mov     rcx, rdi
0x1800469f3  mov     rax, [rax+0C8h]
0x1800469fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800469ff  mov     [rsp+158h+var_C0], rax
0x180046a07  mov     rax, [rdi]
0x180046a0a  mov     rcx, rdi
0x180046a0d  mov     rax, [rax+0C0h]
0x180046a14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046a19  mov     dword ptr [rsp+158h+arg_10], eax
0x180046a20  mov     [rsp+158h+arg_18], r14d
0x180046a28  mov     dword ptr [rsp+158h+var_88], r15d
0x180046a30  lea     rax, aNewframe; "NewFrame"
0x180046a37  mov     [rsp+158h+var_B8], rax
0x180046a3f  lea     rbx, aRdpAvencIc3Cic_1; "Rdp::Avenc::Ic3::CIc3FrameProcessor<str"...
0x180046a46  mov     [rsp+158h+var_A8], rbx
0x180046a4e  mov     dword ptr [rsp+158h+var_90], 32Ah
0x180046a59  lea     r15, aOnecoreuapTerm_23; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180046a60  mov     [rsp+158h+var_C8], r15
0x180046a68  lea     rax, [rsp+158h+var_98]
0x180046a70  mov     [rsp+158h+var_F8], rax
0x180046a75  lea     rax, [rsp+158h+var_C0]
0x180046a7d  mov     [rsp+158h+var_100], rax
0x180046a82  lea     rax, [rsp+158h+arg_10]
0x180046a8a  mov     [rsp+158h+var_108], rax
0x180046a8f  lea     rax, [rsp+158h+arg_18]
0x180046a97  mov     [rsp+158h+var_110], rax
0x180046a9c  lea     rax, [rsp+158h+var_88]
0x180046aa4  mov     [rsp+158h+var_118], rax
0x180046aa9  lea     rax, [rsp+158h+var_B8]
0x180046ab1  mov     [rsp+158h+var_120], rax
0x180046ab6  lea     rax, [rsp+158h+var_A8]
0x180046abe  mov     [rsp+158h+var_128], rax
0x180046ac3  lea     rax, [rsp+158h+var_90]
0x180046acb  mov     [rsp+158h+var_130], rax
0x180046ad0  lea     rax, [rsp+158h+var_C8]
0x180046ad8  mov     qword ptr [rsp+158h+var_138], rax
0x180046add  lea     rdx, unk_1800B1CF8
0x180046ae4  lea     rcx, dword_1800C1058
0x180046aeb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U2@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33444AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &)
0x180046af0  jmp     short loc_180046AF9
0x180046af2  lea     r15, aOnecoreuapTerm_23; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180046af9  mov     [rsp+158h+var_78], 0
0x180046b04  mov     [rsp+158h+var_70], 0
0x180046b10  mov     rax, [rdi]
0x180046b13  mov     rcx, rdi
0x180046b16  mov     rax, [rax+28h]
0x180046b1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046b1f  mov     rax, [rdi]
0x180046b22  lea     rcx, [rsp+158h+var_78]
0x180046b2a  mov     qword ptr [rsp+158h+var_138], rcx
0x180046b2f  lea     r9, [rsp+158h+var_70]
0x180046b37  xor     r8d, r8d
0x180046b3a  xor     edx, edx
0x180046b3c  mov     rcx, rdi
0x180046b3f  mov     rax, [rax+0D0h]
0x180046b46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046b4b  mov     r14d, eax
0x180046b4e  mov     [rsp+158h+arg_18], eax
0x180046b55  mov     rcx, [rsp+158h]; this
0x180046b5d  lea     rax, aFailedToGetMov; "Failed to get moves and dirties"
0x180046b64  mov     qword ptr [rsp+158h+var_138], rax; int
0x180046b69  mov     r9d, r14d; char *
0x180046b6c  mov     r8, r15; unsigned int
0x180046b6f  mov     edx, 33Dh; void *
0x180046b74  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180046b79  lea     rbx, [rsi+100h]
0x180046b80  mov     [rsp+158h+var_50], rbx
0x180046b88  mov     [rsp+158h+var_48], 0
0x180046b90  mov     rcx, rbx
0x180046b93  call    mtx_do_lock
0x180046b98  test    eax, eax
0x180046b9a  jnz     loc_180047A8E
0x180046ba0  mov     eax, [rbx+4Ch]
0x180046ba3  cmp     eax, 7FFFFFFFh
0x180046ba8  jz      loc_180047A96
0x180046bae  mov     [rsp+158h+var_48], 1
0x180046bb6  cmp     qword ptr [rsi+0D0h], 0
0x180046bbe  jz      loc_18004727B
0x180046bc4  mov     rcx, [rsi+0E8h]
0x180046bcb  test    rcx, rcx
0x180046bce  jz      short loc_180046BF1
0x180046bd0  mov     rax, [rcx]
0x180046bd3  mov     rax, [rax+18h]
0x180046bd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046bdc  mov     r15, rax
0x180046bdf  test    rax, rax
0x180046be2  jz      short loc_180046BF1
0x180046be4  mov     rcx, rdi
0x180046be7  call    _anonymous_namespace___GetTimePassedSinceAcquisition_Rdp__Avenc__IFrameSystemBuffer1_
0x180046bec  sub     r15, rax
0x180046bef  jmp     short loc_180046C06
0x180046bf1  mov     rax, [rdi]
0x180046bf4  mov     rcx, rdi
0x180046bf7  mov     rax, [rax+0C8h]
0x180046bfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046c03  mov     r15, rax
0x180046c06  mov     ecx, 0A8h; Size
0x180046c0b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180046c10  mov     [rsp+158h+var_C8], rax
0x180046c18  mov     [rsp+158h+var_80], rax
0x180046c20  mov     rax, [rsp+158h+var_60]
0x180046c28  mov     rcx, [rax]
0x180046c2b  mov     dl, [rcx+120h]
0x180046c31  nop
0x180046c32  test    dl, dl
0x180046c34  jz      short loc_180046C3B
0x180046c36  xor     r14d, r14d
0x180046c39  jmp     short loc_180046C3E
0x180046c3b  mov     r14, [rax]
0x180046c3e  mov     rax, [rax]
0x180046c41  mov     ebx, [rax+80h]
0x180046c47  mov     [rsp+158h+var_98], rdi
0x180046c4f  mov     rax, [rdi]
0x180046c52  mov     rcx, rdi
0x180046c55  mov     rax, [rax+8]
0x180046c59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046c5e  nop
0x180046c5f  mov     dword ptr [rsp+158h+arg_10], 1
0x180046c6a  lea     rax, [rsi+1C0h]
0x180046c71  mov     [rsp+158h+var_128], r15
0x180046c76  mov     [rsp+158h+var_130], r14
0x180046c7b  mov     qword ptr [rsp+158h+var_138], rax
0x180046c80  mov     r8d, ebx
0x180046c83  lea     rdx, [rsp+158h+var_98]
0x180046c8b  mov     rcx, [rsp+158h+var_C8]
0x180046c93  call    ??0CDsStreamSample@Ic3@Avenc@Rdp@@QEAA@AEBV?$com_ptr_t@UIFrameBuffer1@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@IIAEBV?$com_ptr_t@UIFrameAsyncProcessorEvents@Avenc@Rdp@@Uerr_exception_policy@wil@@@5@PEAVCMonitorContext@123@_K@Z; Rdp::Avenc::Ic3::CDsStreamSample::CDsStreamSample(wil::com_ptr_t<Rdp::Avenc::IFrameBuffer1,wil::err_exception_policy> const &,uint,uint,wil::com_ptr_t<Rdp::Avenc::IFrameAsyncProcessorEvents,wil::err_exception_policy> const &,Rdp::Avenc::Ic3::CMonitorContext *,unsigned __int64)
0x180046c98  mov     rbx, rax
0x180046c9b  mov     [rsp+158h+var_80], rax
0x180046ca3  test    rax, rax
0x180046ca6  jz      short loc_180046CC4
0x180046ca8  mov     rcx, [rax+8]
0x180046cac  movsxd  rcx, dword ptr [rcx+4]
0x180046cb0  add     rcx, 8
0x180046cb4  add     rcx, rax
0x180046cb7  mov     rdx, [rcx]
0x180046cba  mov     rax, [rdx+8]
0x180046cbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046cc3  nop
0x180046cc4  mov     rcx, [rsp+158h+var_98]
0x180046ccc  test    rcx, rcx
0x180046ccf  jz      short loc_180046CDE
0x180046cd1  mov     rax, [rcx]
0x180046cd4  mov     rax, [rax+10h]
0x180046cd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046cdd  nop
0x180046cde  mov     eax, cs:dword_1800C1058
0x180046ce4  cmp     eax, r13d
0x180046ce7  jbe     loc_180046DA8
0x180046ced  mov     [rsp+158h+var_C8], r15
0x180046cf5  mov     rax, [rdi]
0x180046cf8  mov     rcx, rdi
0x180046cfb  mov     rax, [rax+0C8h]
0x180046d02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046d07  mov     [rsp+158h+var_A8], rax
0x180046d0f  lea     rax, aMatch; "Match"
0x180046d16  mov     [rsp+158h+var_98], rax
0x180046d1e  lea     rax, aRdpAvencIc3Cic_1; "Rdp::Avenc::Ic3::CIc3FrameProcessor<str"...
0x180046d25  mov     [rsp+158h+var_C0], rax
0x180046d2d  mov     dword ptr [rsp+158h+arg_10], 359h
0x180046d38  lea     rax, aOnecoreuapTerm_23; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180046d3f  mov     [rsp+158h+var_B8], rax
0x180046d47  lea     rax, [rsp+158h+var_C8]
0x180046d4f  mov     [rsp+158h+var_110], rax
0x180046d54  lea     rax, [rsp+158h+var_A8]
0x180046d5c  mov     [rsp+158h+var_118], rax
0x180046d61  lea     rax, [rsp+158h+var_98]
0x180046d69  mov     [rsp+158h+var_120], rax
0x180046d6e  lea     rax, [rsp+158h+var_C0]
0x180046d76  mov     [rsp+158h+var_128], rax
0x180046d7b  lea     rax, [rsp+158h+arg_10]
0x180046d83  mov     [rsp+158h+var_130], rax; char *
0x180046d88  lea     rax, [rsp+158h+var_B8]
0x180046d90  mov     qword ptr [rsp+158h+var_138], rax
0x180046d95  lea     rdx, dword_1800B1BAC
0x180046d9c  lea     rcx, dword_1800C1058
0x180046da3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$07@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$07@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x180046da8  cmp     byte ptr [r12+120h], 0
0x180046db1  jz      loc_180046E55
0x180046db7  mov     r14, [rsi+0F0h]
0x180046dbe  mov     [rsi+0F0h], rbx
0x180046dc5  test    rbx, rbx
0x180046dc8  jz      short loc_180046DE5
0x180046dca  mov     rax, [rbx+8]
0x180046dce  movsxd  rcx, dword ptr [rax+4]
0x180046dd2  add     rcx, 8
0x180046dd6  add     rcx, rbx
0x180046dd9  mov     rax, [rcx]
0x180046ddc  mov     rax, [rax+8]
0x180046de0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046de5  test    r14, r14
0x180046de8  jz      short loc_180046E05
0x180046dea  mov     rax, [r14+8]
0x180046dee  movsxd  rcx, dword ptr [rax+4]
0x180046df2  add     rcx, 8
0x180046df6  add     rcx, r14
0x180046df9  mov     rax, [rcx]
0x180046dfc  mov     rax, [rax+10h]
0x180046e00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046e05  mov     [rsp+158h+arg_10], 0
0x180046e11  lea     rcx, [rsp+158h+arg_10]
0x180046e19  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x180046e1f  mov     eax, dword ptr [rsp+158h+arg_10+4]
0x180046e26  shl     rax, 20h
0x180046e2a  mov     ecx, dword ptr [rsp+158h+arg_10]
0x180046e31  mov     rdx, 0FE624E212AC18000h
0x180046e3b  add     rax, rdx
0x180046e3e  add     rcx, rax
0x180046e41  mov     [rsi+1A8h], rcx
0x180046e48  lea     rcx, [rsi+158h]; ConditionVariable
0x180046e4f  call    cs:__imp_WakeConditionVariable
0x180046e55  mov     rax, [rsi+0D0h]
0x180046e5c  mov     r14, [rax+118h]
0x180046e63  mov     [rsp+158h+var_58], r14
0x180046e6b  test    r14, r14
0x180046e6e  jz      short loc_180046E8C
0x180046e70  mov     rax, [r14+8]
0x180046e74  movsxd  rcx, dword ptr [rax+4]
0x180046e78  add     rcx, 8
0x180046e7c  add     rcx, r14
0x180046e7f  mov     rax, [rcx]
0x180046e82  mov     rax, [rax+8]
0x180046e86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046e8b  nop
0x180046e8c  test    r14, r14
0x180046e8f  jz      loc_180047199
0x180046e95  mov     rax, [rdi]
0x180046e98  mov     rcx, rdi
0x180046e9b  mov     rax, [rax+0C8h]
0x180046ea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046ea7  mov     r8, r15
0x180046eaa  mov     rdx, rax
0x180046ead  mov     rcx, rsi
0x180046eb0  call    ?CheckFirstFrameAndRaiseEvent@?$CIc3FrameProcessor@UICpuFrameProcessor@Avenc@Rdp@@UICpuFrameAsyncProcessor@23@@Ic3@Avenc@Rdp@@IEAA_N_K0@Z; Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::ICpuFrameProcessor,Rdp::Avenc::ICpuFrameAsyncProcessor>::CheckFirstFrameAndRaiseEvent(unsigned __int64,unsigned __int64)
0x180046eb5  mov     byte ptr [rsp+158h+arg_10], al
0x180046ebc  mov     ecx, cs:dword_1800C1058
0x180046ec2  cmp     ecx, r13d
0x180046ec5  jbe     loc_180046FA9
0x180046ecb  mov     rcx, [rdi]
0x180046ece  mov     rax, [rcx+0C8h]
0x180046ed5  mov     rcx, rdi
0x180046ed8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046edd  mov     [rsp+158h+var_C8], rax
0x180046ee5  mov     eax, [rsp+158h+var_B0]
0x180046eec  mov     [rsp+158h+arg_18], eax
0x180046ef3  mov     eax, [rsp+158h+var_AC]
0x180046efa  mov     dword ptr [rsp+158h+var_90], eax
0x180046f01  lea     rax, aStart; "Start"
0x180046f08  mov     [rsp+158h+var_A8], rax
0x180046f10  lea     rax, aRdpAvencIc3Cic_1; "Rdp::Avenc::Ic3::CIc3FrameProcessor<str"...
0x180046f17  mov     [rsp+158h+var_98], rax
0x180046f1f  mov     dword ptr [rsp+158h+var_88], 36Dh
0x180046f2a  lea     r15, aOnecoreuapTerm_23; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180046f31  mov     [rsp+158h+var_C0], r15
0x180046f39  lea     rax, [rsp+158h+var_C8]
0x180046f41  mov     [rsp+158h+var_108], rax
0x180046f46  lea     rax, [rsp+158h+arg_18]
0x180046f4e  mov     [rsp+158h+var_110], rax
0x180046f53  lea     rax, [rsp+158h+var_90]
0x180046f5b  mov     [rsp+158h+var_118], rax
0x180046f60  lea     rax, [rsp+158h+var_A8]
  ... truncated ...
```
