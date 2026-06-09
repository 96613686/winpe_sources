# Rdp::Avenc::SinkWriter::CSinkWriterFrameProcessor::ProcessFrameInternal<Rdp::Avenc::IFrameDxBuffer>(Rdp::Avenc::IFrameDxBuffer &,bool *)

- ea: `0x180035720`
- end: `0x180035cdb`
- name: `??$ProcessFrameInternal@UIFrameDxBuffer@Avenc@Rdp@@@CSinkWriterFrameProcessor@SinkWriter@Avenc@Rdp@@IEAAJAEAUIFrameDxBuffer@23@PEA_N@Z`
- size: `1467`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180035230`

## callees

- `0x18000154c`
- `0x1800032cc`
- `0x180003418`
- `0x1800039dc`
- `0x18000a1b4`
- `0x18000ec04`
- `0x180026864`
- `0x18002b84c`
- `0x180035720`
- `0x18003670c`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-perfcounters-l1-1-0!PerfIncrementULongCounterValue` at `0x1800358c2`
- `api-ms-win-core-perfcounters-l1-1-0!PerfIncrementULongCounterValue` at `0x1800358c2`

## string_xrefs

- `0x180035cc8`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x1800358df`: `onecoreuap\termsrv\rdp_bin\win\common/inc/PerfMon.h`
- `0x18003575f`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\sinkwriterprocessor\sinkwriterframeprocessor.cpp`
- `0x1800357d0`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\sinkwriterprocessor\sinkwriterframeprocessor.cpp`
- `0x180035835`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\sinkwriterprocessor\sinkwriterframeprocessor.cpp`
- `0x180035b5a`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\sinkwriterprocessor\sinkwriterframeprocessor.cpp`
- `0x1800357b6`: `Rdp::Avenc::SinkWriter::CSinkWriterFrameProcessor::ProcessFrameInternal`
- `0x18003583c`: `Rdp::Avenc::SinkWriter::CSinkWriterFrameProcessor::ProcessFrameInternal`
- `0x180035b61`: `Rdp::Avenc::SinkWriter::CSinkWriterFrameProcessor::ProcessFrameInternal`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Rdp::Avenc::SinkWriter::CSinkWriterFrameProcessor::ProcessFrameInternal<Rdp::Avenc::IFrameDxBuffer>(
        __int64 a1,
        __int64 a2,
        bool *a3)
{
  bool *v3; // r12
  __int64 v4; // rbx
  int v7; // r8d
  int v8; // r9d
  __int64 *v9; // r15
  __int64 v10; // rdi
  __int64 v11; // rax
  volatile signed __int32 *v12; // rdi
  ULONG v13; // eax
  int v14; // r8d
  int v15; // r9d
  int v16; // eax
  int v17; // r8d
  int v18; // r9d
  const char *v19; // r9
  unsigned int v20; // r14d
  unsigned int v21; // edi
  int v22; // eax
  __int64 v23; // rdx
  int v24; // r8d
  int v25; // r9d
  wil *v26; // rcx
  int v27; // r13d
  int v28; // eax
  __int64 v29; // rcx
  int v30; // [rsp+20h] [rbp-F8h]
  int v31; // [rsp+20h] [rbp-F8h]
  const char *v32; // [rsp+28h] [rbp-F0h]
  struct Rdp::Avenc::IFrameBuffer1 *v33; // [rsp+90h] [rbp-88h] BYREF
  const char *v34; // [rsp+98h] [rbp-80h] BYREF
  const char *v35; // [rsp+A0h] [rbp-78h] BYREF
  const char *v36; // [rsp+A8h] [rbp-70h] BYREF
  const char *v37; // [rsp+B0h] [rbp-68h] BYREF
  const char *v38; // [rsp+B8h] [rbp-60h] BYREF
  _QWORD v39[11]; // [rsp+C0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]
  bool *v43; // [rsp+130h] [rbp+18h] BYREF
  unsigned int v44; // [rsp+138h] [rbp+20h] BYREF

  v43 = a3;
  v3 = a3;
  v4 = a2;
  if ( a3 )
  {
    v44 = 0;
    if ( (unsigned int)dword_1800C1058 > 5 )
    {
      LODWORD(v34) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 120LL))(a2);
      v37 = "NewFrame";
      v36 = "Rdp::Avenc::SinkWriter::CSinkWriterFrameProcessor::ProcessFrameInternal";
      LODWORD(v33) = 205;
      v35 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterframeprocessor.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)&byte_1800AF327,
        v7,
        v8,
        (__int64)&v35,
        (__int64)&v33,
        (__int64)&v36,
        (__int64)&v37,
        (__int64)&v34);
    }
    v9 = (__int64 *)(a1 + 104);
    v39[0] = a1 + 104;
    v10 = *(_QWORD *)(*(_QWORD *)(a1 + 104) + 112LL);
    v11 = *(_QWORD *)(v10 + 320);
    if ( v11 )
      _InterlockedIncrement((volatile signed __int32 *)(v11 + 8));
    try
    {
      v35 = *(const char **)(v10 + 312);
      v39[1] = v35;
      v12 = *(volatile signed __int32 **)(v10 + 320);
      v39[2] = v12;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 40LL))(v4);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 56LL))(v4);
      v13 = PerfIncrementULongCounterValue(*(HANDLE *)v35, *((PPERF_COUNTERSET_INSTANCE *)v35 + 3), 1u, 1u);
      wil::details::in1diag3::Throw_IfWin32ErrorMsg(
        retaddr,
        (void *)0x18B,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/PerfMon.h",
        (const char *)v13,
        (unsigned int)"PerfIncrementULongCounterValue failed",
        v32);
      if ( Rdp::Avenc::ClientFrameRateTracker::IsClientStalled(*(Rdp::Avenc::ClientFrameRateTracker **)(a1 + 136)) )
      {
        if ( (unsigned int)dword_1800C1058 > 4 )
        {
          LODWORD(v33) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 120LL))(v4);
          v35 = (const char *)(*v9 + 120);
          v36 = "Client stall detected. Skipping frame";
          v37 = "Rdp::Avenc::SinkWriter::CSinkWriterFrameProcessor::ProcessFrameInternal";
          LODWORD(v34) = 232;
          v38 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterframeprocessor.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_1800C1058,
            (unsigned int)byte_1800AF27D,
            v17,
            v18,
            (__int64)&v38,
            (__int64)&v34,
            (__int64)&v37,
            (__int64)&v36,
            (__int64)&v35,
            (__int64)&v33);
        }
      }
      else
      {
        v33 = 0;
        v16 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct Rdp::Avenc::IFrameBuffer1 **))v4)(
                v4,
                &GUID_5ce16a4c_4058_480b_8806_9c82986f8662,
                &v33);
        if ( v16 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x1CBE,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
            (const char *)(unsigned int)v16,
            v31);
        Rdp::Avenc::SinkWriter::CMFEncoder::EncodeFrame(*(Rdp::Avenc::SinkWriter::CMFEncoder **)(a1 + 128), v33, &v44);
        if ( v33 )
          (*(void (__fastcall **)(struct Rdp::Avenc::IFrameBuffer1 *))(*(_QWORD *)v33 + 16LL))(v33);
      }
      if ( (unsigned int)dword_1800C1058 > 5 )
      {
        v38 = *(const char **)(*(_QWORD *)(a1 + 136) + 136LL);
        v35 = (const char *)(*v9 + 120);
        v36 = "FrameRate";
        v37 = "Rdp::Avenc::SinkWriter::CSinkWriterFrameProcessor::ProcessFrameInternal";
        LODWORD(v33) = 237;
        v34 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterframeprocessor.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_1800C1058,
          (unsigned int)&byte_1800AF2D7,
          v14,
          v15,
          (__int64)&v34,
          (__int64)&v33,
          (__int64)&v37,
          (__int64)&v36,
          (__int64)&v35,
          (__int64)&v38);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 48LL))(v4);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 64LL))(v4);
      v20 = 1;
      if ( v12 )
      {
        if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
          if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
        }
      }
      v21 = 0;
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0xFC,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterframeprocessor.cpp",
        v19);
      v27 = wil::ResultFromCaughtException(v26);
      LODWORD(v34) = v27;
      LODWORD(v33) = 2;
      v28 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 120LL))(a2);
      v29 = *(_QWORD *)(a1 + 104);
      Rdp::Modern::Utils::CInflightRecorder::pushN(
        (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
        (wchar_t *)L"Frame dropped: Id {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}, FrameNumber: %d, Error: %#x",
        "Rdp::Avenc::SinkWriter::CSinkWriterFrameProcessor::ProcessFrameInternal",
        "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterframeprocessor.cpp",
        0x109u,
        *(_DWORD *)(v29 + 120),
        *(unsigned __int16 *)(v29 + 124),
        *(unsigned __int16 *)(v29 + 126),
        *(unsigned __int8 *)(v29 + 128),
        *(unsigned __int8 *)(v29 + 129),
        *(unsigned __int8 *)(v29 + 130),
        *(unsigned __int8 *)(v29 + 131),
        *(unsigned __int8 *)(v29 + 132),
        *(unsigned __int8 *)(v29 + 133),
        *(unsigned __int8 *)(v29 + 134),
        *(unsigned __int8 *)(v29 + 135),
        v28,
        v27);
      v3 = v43;
      v4 = a2;
      v20 = (unsigned int)v33;
      v21 = (unsigned int)v34;
      v9 = (__int64 *)v39[0];
    }
    v22 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v4 + 112LL))(v4, v20, v44, 0);
    if ( v22 < 0 && (unsigned int)dword_1800C1058 > 2 )
    {
      LODWORD(v43) = v22;
      v44 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 120LL))(v4);
      v23 = *v9;
      LODWORD(v33) = *(_DWORD *)(*(_QWORD *)(*v9 + 112) + 160LL);
      v39[0] = v23 + 120;
      v38 = "Failed to report frame statistics";
      v35 = "Rdp::Avenc::SinkWriter::CSinkWriterFrameProcessor::ProcessFrameInternal";
      LODWORD(v34) = 285;
      v36 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterframeprocessor.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)&word_1800AF1B6,
        v24,
        v25,
        (__int64)&v36,
        (__int64)&v34,
        (__int64)&v35,
        (__int64)&v38,
        (__int64)v39,
        (__int64)&v33,
        (__int64)&v44,
        (__int64)&v43);
    }
    *v3 = v20 != 1;
    return v21;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC5,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterframeprocessor.cpp",
      (const char *)0x80004003LL,
      v30);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x180035720  mov     [rsp+arg_10], r8
0x180035725  mov     [rsp+arg_8], rdx
0x18003572a  mov     [rsp+arg_0], rcx
0x18003572f  push    rbx
0x180035730  push    rsi
0x180035731  push    rdi
0x180035732  push    r12
0x180035734  push    r13
0x180035736  push    r14
0x180035738  push    r15
0x18003573a  sub     rsp, 0E0h
0x180035741  mov     r12, r8
0x180035744  mov     rbx, rdx
0x180035747  mov     r14, rcx
0x18003574a  test    r8, r8
0x18003574d  jnz     short loc_180035777
0x18003574f  mov     rcx, [rsp+118h]; this
0x180035757  mov     ebx, 80004003h
0x18003575c  mov     r9d, ebx; char *
0x18003575f  lea     r8, aOnecoreuapTerm_10; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180035766  mov     edx, 0C5h; void *
0x18003576b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035770  mov     eax, ebx
0x180035772  jmp     loc_180035CB2
0x180035777  mov     [rsp+118h+arg_18], 0
0x180035782  mov     eax, cs:dword_1800C1058
0x180035788  cmp     eax, 5
0x18003578b  jbe     loc_180035835
0x180035791  mov     rax, [rdx]
0x180035794  mov     rcx, rbx
0x180035797  mov     rax, [rax+78h]
0x18003579b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800357a0  mov     dword ptr [rsp+118h+var_80], eax
0x1800357a7  lea     rax, aNewframe; "NewFrame"
0x1800357ae  mov     [rsp+118h+var_68], rax
0x1800357b6  lea     r13, aRdpAvencSinkwr_5; "Rdp::Avenc::SinkWriter::CSinkWriterFram"...
0x1800357bd  mov     [rsp+118h+var_70], r13
0x1800357c5  mov     dword ptr [rsp+118h+var_88], 0CDh
0x1800357d0  lea     rsi, aOnecoreuapTerm_10; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x1800357d7  mov     [rsp+118h+var_78], rsi
0x1800357df  lea     rax, [rsp+118h+var_80]
0x1800357e7  mov     [rsp+118h+var_D8], rax
0x1800357ec  lea     rax, [rsp+118h+var_68]
0x1800357f4  mov     [rsp+118h+var_E0], rax
0x1800357f9  lea     rax, [rsp+118h+var_70]
0x180035801  mov     [rsp+118h+var_E8], rax
0x180035806  lea     rax, [rsp+118h+var_88]
0x18003580e  mov     [rsp+118h+var_F0], rax
0x180035813  lea     rax, [rsp+118h+var_78]
0x18003581b  mov     qword ptr [rsp+118h+var_F8], rax
0x180035820  lea     rdx, byte_1800AF327
0x180035827  lea     rcx, dword_1800C1058
0x18003582e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180035833  jmp     short loc_180035843
0x180035835  lea     rsi, aOnecoreuapTerm_10; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18003583c  lea     r13, aRdpAvencSinkwr_5; "Rdp::Avenc::SinkWriter::CSinkWriterFram"...
0x180035843  lea     r15, [r14+68h]
0x180035847  mov     [rsp+118h+var_58], r15
0x18003584f  mov     rax, [r15]
0x180035852  mov     rdi, [rax+70h]
0x180035856  mov     rax, [rdi+140h]
0x18003585d  test    rax, rax
0x180035860  jz      short loc_180035866
0x180035862  lock inc dword ptr [rax+8]
0x180035866  mov     rax, [rdi+138h]
0x18003586d  mov     [rsp+118h+var_78], rax
0x180035875  mov     [rsp+118h+var_50], rax
0x18003587d  mov     rdi, [rdi+140h]
0x180035884  mov     [rsp+118h+var_48], rdi
0x18003588c  mov     rax, [rbx]
0x18003588f  mov     rcx, rbx
0x180035892  mov     rax, [rax+28h]
0x180035896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003589b  mov     rax, [rbx]
0x18003589e  mov     rcx, rbx
0x1800358a1  mov     rax, [rax+38h]
0x1800358a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800358aa  mov     r9d, 1; Value
0x1800358b0  mov     r8d, r9d; CounterId
0x1800358b3  mov     rcx, [rsp+118h+var_78]
0x1800358bb  mov     rdx, [rcx+18h]; Instance
0x1800358bf  mov     rcx, [rcx]; Provider
0x1800358c2  call    cs:__imp_PerfIncrementULongCounterValue
0x1800358c8  mov     rcx, [rsp+118h]; this
0x1800358d0  lea     rdx, aPerfincrementu; "PerfIncrementULongCounterValue failed"
0x1800358d7  mov     qword ptr [rsp+118h+var_F8], rdx; int
0x1800358dc  mov     r9d, eax; char *
0x1800358df  lea     r8, aOnecoreuapTerm_29; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x1800358e6  mov     edx, 18Bh; void *
0x1800358eb  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x1800358f0  mov     rcx, [r14+88h]; this
0x1800358f7  call    ?IsClientStalled@ClientFrameRateTracker@Avenc@Rdp@@QEAA_NXZ; Rdp::Avenc::ClientFrameRateTracker::IsClientStalled(void)
0x1800358fc  test    al, al
0x1800358fe  jnz     short loc_180035975
0x180035900  mov     [rsp+118h+var_88], 0
0x18003590c  mov     rax, [rbx]
0x18003590f  lea     r8, [rsp+118h+var_88]
0x180035917  lea     rdx, _GUID_5ce16a4c_4058_480b_8806_9c82986f8662
0x18003591e  mov     rcx, rbx
0x180035921  mov     rax, [rax]
0x180035924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035929  mov     rcx, [rsp+118h]; this
0x180035931  test    eax, eax
0x180035933  js      loc_180035CC5
0x180035939  lea     r8, [rsp+118h+arg_18]; unsigned int *
0x180035941  mov     rdx, [rsp+118h+var_88]; struct Rdp::Avenc::IFrameBuffer1 *
0x180035949  mov     rcx, [r14+80h]; this
0x180035950  call    ?EncodeFrame@CMFEncoder@SinkWriter@Avenc@Rdp@@QEAAXPEAUIFrameBuffer1@34@AEAI@Z; Rdp::Avenc::SinkWriter::CMFEncoder::EncodeFrame(Rdp::Avenc::IFrameBuffer1 *,uint &)
0x180035955  nop
0x180035956  mov     rcx, [rsp+118h+var_88]
0x18003595e  test    rcx, rcx
0x180035961  jz      short loc_180035970
0x180035963  mov     rax, [rcx]
0x180035966  mov     rax, [rax+10h]
0x18003596a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003596f  nop
0x180035970  jmp     loc_180035A34
0x180035975  mov     eax, cs:dword_1800C1058
0x18003597b  cmp     eax, 4
0x18003597e  jbe     loc_180035A34
0x180035984  mov     rax, [rbx]
0x180035987  mov     rcx, rbx
0x18003598a  mov     rax, [rax+78h]
0x18003598e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035993  mov     dword ptr [rsp+118h+var_88], eax
0x18003599a  mov     rax, [r15]
0x18003599d  add     rax, 78h ; 'x'
0x1800359a1  mov     [rsp+118h+var_78], rax
0x1800359a9  lea     rax, aClientStallDet; "Client stall detected. Skipping frame"
0x1800359b0  mov     [rsp+118h+var_70], rax
0x1800359b8  mov     [rsp+118h+var_68], r13
0x1800359c0  mov     dword ptr [rsp+118h+var_80], 0E8h
0x1800359cb  mov     [rsp+118h+var_60], rsi
0x1800359d3  lea     rax, [rsp+118h+var_88]
0x1800359db  mov     [rsp+118h+var_D0], rax
0x1800359e0  lea     rax, [rsp+118h+var_78]
0x1800359e8  mov     [rsp+118h+var_D8], rax
0x1800359ed  lea     rax, [rsp+118h+var_70]
0x1800359f5  mov     [rsp+118h+var_E0], rax
0x1800359fa  lea     rax, [rsp+118h+var_68]
0x180035a02  mov     [rsp+118h+var_E8], rax
0x180035a07  lea     rax, [rsp+118h+var_80]
0x180035a0f  mov     [rsp+118h+var_F0], rax
0x180035a14  lea     rax, [rsp+118h+var_60]
0x180035a1c  mov     qword ptr [rsp+118h+var_F8], rax
0x180035a21  lea     rdx, byte_1800AF27D
0x180035a28  lea     rcx, dword_1800C1058
0x180035a2f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByRef@$0BA@@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByRef@$0BA@@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x180035a34  mov     eax, cs:dword_1800C1058
0x180035a3a  cmp     eax, 5
0x180035a3d  jbe     loc_180035AF5
0x180035a43  mov     rax, [r14+88h]
0x180035a4a  movsd   xmm0, qword ptr [rax+88h]
0x180035a52  movsd   [rsp+118h+var_60], xmm0
0x180035a5b  mov     rax, [r15]
0x180035a5e  add     rax, 78h ; 'x'
0x180035a62  mov     [rsp+118h+var_78], rax
0x180035a6a  lea     rax, aFramerate; "FrameRate"
0x180035a71  mov     [rsp+118h+var_70], rax
0x180035a79  mov     [rsp+118h+var_68], r13
0x180035a81  mov     dword ptr [rsp+118h+var_88], 0EDh
0x180035a8c  mov     [rsp+118h+var_80], rsi
0x180035a94  lea     rax, [rsp+118h+var_60]
0x180035a9c  mov     [rsp+118h+var_D0], rax
0x180035aa1  lea     rax, [rsp+118h+var_78]
0x180035aa9  mov     [rsp+118h+var_D8], rax
0x180035aae  lea     rax, [rsp+118h+var_70]
0x180035ab6  mov     [rsp+118h+var_E0], rax
0x180035abb  lea     rax, [rsp+118h+var_68]
0x180035ac3  mov     [rsp+118h+var_E8], rax
0x180035ac8  lea     rax, [rsp+118h+var_88]
0x180035ad0  mov     [rsp+118h+var_F0], rax
0x180035ad5  lea     rax, [rsp+118h+var_80]
0x180035add  mov     qword ptr [rsp+118h+var_F8], rax
0x180035ae2  lea     rdx, byte_1800AF2D7
0x180035ae9  lea     rcx, dword_1800C1058
0x180035af0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &)
0x180035af5  mov     rax, [rbx]
0x180035af8  mov     rcx, rbx
0x180035afb  mov     rax, [rax+30h]
0x180035aff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035b04  mov     rax, [rbx]
0x180035b07  mov     rcx, rbx
0x180035b0a  mov     rax, [rax+40h]
0x180035b0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035b13  mov     r14d, 1
0x180035b19  test    rdi, rdi
0x180035b1c  jz      short loc_180035B56
0x180035b1e  or      eax, 0FFFFFFFFh
0x180035b21  lock xadd [rdi+8], eax
0x180035b26  cmp     eax, r14d
0x180035b29  jnz     short loc_180035B56
0x180035b2b  mov     rax, [rdi]
0x180035b2e  mov     rcx, rdi
0x180035b31  mov     rax, [rax]
0x180035b34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035b39  or      eax, 0FFFFFFFFh
0x180035b3c  lock xadd [rdi+0Ch], eax
0x180035b41  cmp     eax, r14d
0x180035b44  jnz     short loc_180035B56
0x180035b46  mov     rax, [rdi]
0x180035b49  mov     rcx, rdi
0x180035b4c  mov     rax, [rax+8]
0x180035b50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035b55  nop
0x180035b56  xor     edi, edi
0x180035b58  jmp     short loc_180035B8F
0x180035b5a  lea     rsi, aOnecoreuapTerm_10; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180035b61  lea     r13, aRdpAvencSinkwr_5; "Rdp::Avenc::SinkWriter::CSinkWriterFram"...
0x180035b68  mov     r12, [rsp+118h+arg_10]
0x180035b70  mov     rbx, [rsp+118h+arg_8]
0x180035b78  mov     r14d, dword ptr [rsp+118h+var_88]
0x180035b80  mov     edi, dword ptr [rsp+118h+var_80]
0x180035b87  mov     r15, [rsp+118h+var_58]
0x180035b8f  mov     rax, [rbx]
0x180035b92  xor     r9d, r9d
0x180035b95  mov     r8d, [rsp+118h+arg_18]
0x180035b9d  mov     edx, r14d
0x180035ba0  mov     rcx, rbx
0x180035ba3  mov     rax, [rax+70h]
0x180035ba7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035bac  test    eax, eax
0x180035bae  jns     loc_180035CA5
0x180035bb4  mov     ecx, cs:dword_1800C1058
0x180035bba  cmp     ecx, 2
0x180035bbd  jbe     loc_180035CA5
0x180035bc3  mov     dword ptr [rsp+118h+arg_10], eax
0x180035bca  mov     rax, [rbx]
0x180035bcd  mov     rcx, rbx
0x180035bd0  mov     rax, [rax+78h]
0x180035bd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035bd9  mov     [rsp+118h+arg_18], eax
0x180035be0  mov     rdx, [r15]
0x180035be3  mov     rax, [rdx+70h]
0x180035be7  mov     ecx, [rax+0A0h]
0x180035bed  mov     dword ptr [rsp+118h+var_88], ecx
0x180035bf4  lea     rax, [rdx+78h]
0x180035bf8  mov     [rsp+118h+var_58], rax
0x180035c00  lea     rax, aFailedToReport; "Failed to report frame statistics"
0x180035c07  mov     [rsp+118h+var_60], rax
0x180035c0f  mov     [rsp+118h+var_78], r13
0x180035c17  mov     dword ptr [rsp+118h+var_80], 11Dh
0x180035c22  mov     [rsp+118h+var_70], rsi
0x180035c2a  lea     rax, [rsp+118h+arg_10]
0x180035c32  mov     [rsp+118h+var_C0], rax
0x180035c37  lea     rax, [rsp+118h+arg_18]
0x180035c3f  mov     [rsp+118h+var_C8], rax
0x180035c44  lea     rax, [rsp+118h+var_88]
0x180035c4c  mov     [rsp+118h+var_D0], rax
0x180035c51  lea     rax, [rsp+118h+var_58]
0x180035c59  mov     [rsp+118h+var_D8], rax
0x180035c5e  lea     rax, [rsp+118h+var_60]
0x180035c66  mov     [rsp+118h+var_E0], rax
0x180035c6b  lea     rax, [rsp+118h+var_78]
0x180035c73  mov     [rsp+118h+var_E8], rax
0x180035c78  lea     rax, [rsp+118h+var_80]
0x180035c80  mov     [rsp+118h+var_F0], rax
0x180035c85  lea     rax, [rsp+118h+var_70]
0x180035c8d  mov     qword ptr [rsp+118h+var_F8], rax
0x180035c92  lea     rdx, word_1800AF1B6
0x180035c99  lea     rcx, dword_1800C1058
0x180035ca0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByRef@$0BA@@@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByRef@$0BA@@@444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180035ca5  cmp     r14d, 1
0x180035ca9  setnz   cl
0x180035cac  mov     [r12], cl
0x180035cb0  mov     eax, edi
0x180035cb2  add     rsp, 0E0h
0x180035cb9  pop     r15
0x180035cbb  pop     r14
0x180035cbd  pop     r13
0x180035cbf  pop     r12
0x180035cc1  pop     rdi
0x180035cc2  pop     rsi
0x180035cc3  pop     rbx
0x180035cc4  retn
0x180035cc5  mov     r9d, eax; char *
0x180035cc8  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180035ccf  mov     edx, 1CBEh; void *
0x180035cd4  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
