# Rdp::Avenc::SinkWriter::CSinkWriterFrameProcessor::Start(void)

- ea: `0x180038380`
- end: `0x180038832`
- name: `?Start@CSinkWriterFrameProcessor@SinkWriter@Avenc@Rdp@@UEAAJXZ`
- size: `1202`
- prototype: `int(Rdp::Avenc::SinkWriter::CSinkWriterFrameProcessor *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180035690`

## callees

- `0x180003604`
- `0x1800065a4`
- `0x18001143c`
- `0x180011490`
- `0x1800152c4`
- `0x180015480`
- `0x180022fb8`
- `0x180023b34`
- `0x180023ee4`
- `0x18002b904`
- `0x18002dd40`
- `0x18002e0c4`
- `0x180038380`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800383e6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800387a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800383e6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800387a7`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180038650`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180038650`

## string_xrefs

- `0x1800386c7`: `onecoreuap\termsrv\rdp_bin\win\common/protocol/RdpEgfx/RdpEgfx.h`
- `0x1800386b0`: `Unable to ensure RDPGFX_CREATE_SURFACE_PDU_SIZE`
- `0x18003847c`: `Start SinkWriter frame processor`
- `0x180038529`: `Rdp::Avenc::SinkWriter::CSinkWriterFrameProcessor::Start`
- `0x180038522`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\sinkwriterprocessor\sinkwriterframeprocessor.cpp`
- `0x180038571`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\sinkwriterprocessor\sinkwriterframeprocessor.cpp`
- `0x180038530`: `SinkWriterFrameProcessorStart`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Rdp::Avenc::SinkWriter::CSinkWriterFrameProcessor::Start(
        Rdp::Avenc::SinkWriter::CSinkWriterFrameProcessor *this,
        __int64 a2,
        int a3,
        int a4)
{
  char v5; // di
  char v6; // bl
  bool v7; // si
  char CurrentThreadId; // al
  int v9; // r8d
  int v10; // edx
  __int64 v11; // rdx
  __int64 v12; // r14
  char *v13; // rsi
  __int64 v14; // rax
  const char *v15; // r9
  volatile signed __int32 *v16; // rbx
  Rdp::Avenc::CFcWireEncoderWithBulkUncompressed *v17; // rsi
  _DWORD *v18; // rax
  int v19; // r13d
  _DWORD *v20; // r14
  __int64 v21; // r8
  int v22; // edx
  unsigned int v23; // edx
  bool v24; // si
  char v25; // al
  int v26; // r8d
  int v27; // edx
  __int64 result; // rax
  int v29; // [rsp+20h] [rbp-A8h]
  __int64 *v30; // [rsp+20h] [rbp-A8h]
  int v31; // [rsp+28h] [rbp-A0h]
  const char *v32; // [rsp+28h] [rbp-A0h]
  int *v33; // [rsp+60h] [rbp-68h] BYREF
  const char *v34; // [rsp+68h] [rbp-60h] BYREF
  __int64 v35; // [rsp+70h] [rbp-58h] BYREF
  const char *v36; // [rsp+78h] [rbp-50h] BYREF
  char *v37; // [rsp+80h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]
  int v39; // [rsp+D8h] [rbp+10h] BYREF
  __int64 v40; // [rsp+E0h] [rbp+18h] BYREF
  const char *v41; // [rsp+E8h] [rbp+20h] BYREF

  v5 = 1;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || (v6 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u) )
  {
    v6 = 0;
  }
  v7 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v9) = v7;
    LOBYTE(v10) = v6;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v10,
      v9,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v29,
      v31,
      10,
      &WPP_dce8caabb58138b44d6f1d43a0cfbbf0_Traceguids,
      CurrentThreadId);
  }
  if ( (unsigned int)dword_1800C1058 > 4
    && (qword_1800C1068 & 0x470000000000LL) != 0
    && (qword_1800C1070 & 0x470000000000LL) == qword_1800C1070 )
  {
    v11 = *((_QWORD *)this + 3);
    v39 = *(_DWORD *)(*(_QWORD *)(v11 + 112) + 160LL);
    v40 = v11 + 120;
    v41 = "Start SinkWriter frame processor";
    v33 = &xmmword_1800C21A0;
    v34 = "RdpAvenc";
    v35 = 0x1000000;
    v36 = "Checkpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_1800C1058,
      (unsigned int)&byte_1800AF47F,
      a3,
      a4,
      (__int64)&v36,
      (__int64)&v35,
      (__int64)&v34,
      (__int64)&v33,
      (__int64)&v41,
      (__int64)&v40,
      (__int64)&v39);
  }
  try
  {
    Rdp::Modern::Utils::CInflightRecorder::push0(
      (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      L"SinkWriterFrameProcessorStart",
      "Rdp::Avenc::SinkWriter::CSinkWriterFrameProcessor::Start",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterframeprocessor.cpp",
      0x3Fu);
    v32 = "Graphics file I/O channel is not available";
    v30 = (__int64 *)(*(_QWORD *)(*((_QWORD *)this + 3) + 112LL) + 288LL);
    wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(
      retaddr,
      66,
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterframeprocessor.cpp",
      2147500035LL);
    v12 = *v30;
    v13 = (char *)operator new(0x70u);
    *((_DWORD *)v13 + 2) = 1;
    *((_DWORD *)v13 + 3) = 1;
    *(_QWORD *)v13 = &std::_Ref_count_obj2<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>>::`vftable';
    *((_QWORD *)v13 + 2) = &Rdp::Protocol::CRdpCtrl_Src<Rdp::Avenc::CFcWireEncoder>::`vftable';
    *((_QWORD *)v13 + 3) = v12;
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
    *((_QWORD *)v13 + 4) = 0;
    *((_QWORD *)v13 + 5) = 0;
    *((_QWORD *)v13 + 6) = 0;
    *((_QWORD *)v13 + 7) = 0;
    *((_QWORD *)v13 + 8) = 0;
    *((_QWORD *)v13 + 9) = 0;
    *((_QWORD *)v13 + 10) = 0;
    *((_QWORD *)v13 + 11) = 0;
    *((_QWORD *)v13 + 12) = 0;
    *((_QWORD *)v13 + 2) = &Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>::`vftable';
    *((_DWORD *)v13 + 26) = 0;
    v36 = v13 + 16;
    v37 = v13;
    std::atomic<std::shared_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>>>::store(
      (char *)this + 32,
      &v36);
    v14 = std::_Locked_pointer<std::_Ref_count_base>::_Lock_and_load((char *)this + 40);
    v16 = (volatile signed __int32 *)v14;
    v17 = (Rdp::Avenc::CFcWireEncoderWithBulkUncompressed *)*((_QWORD *)this + 4);
    v36 = (const char *)v17;
    v37 = (char *)v14;
    if ( v14 )
      _InterlockedAdd((volatile signed __int32 *)(v14 + 8), 1u);
    if ( (_InterlockedExchange64((volatile __int64 *)this + 5, v14) & 3) == 2 )
      WakeByAddressAll((char *)this + 40);
    if ( v17 )
    {
      Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::AllocatePool(v17, 0x1000u, 0, 0);
      v18 = (_DWORD *)*((_QWORD *)this + 3);
      v19 = v18[38];
      LODWORD(v40) = v18[37];
      v39 = v18[34];
      v20 = Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::EnsureBuffer(v17, 0xFu);
      wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(
        retaddr,
        266,
        "onecoreuap\\termsrv\\rdp_bin\\win\\common/protocol/RdpEgfx/RdpEgfx.h",
        2147942414LL,
        v20,
        "Unable to ensure RDPGFX_CREATE_SURFACE_PDU_SIZE");
      *v20 = 9;
      v20[1] = 15;
      *((_WORD *)v20 + 4) = v39;
      *((_WORD *)v20 + 5) = v40;
      *((_WORD *)v20 + 6) = v19;
      *((_BYTE *)v20 + 14) = 33;
      v21 = *((_QWORD *)this + 3);
      Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>::MapSurfaceToScaledOutput(
        (_DWORD)v17,
        v22,
        *(_DWORD *)(v21 + 136),
        *(_DWORD *)(*(_QWORD *)(v21 + 112) + 164LL),
        *(_DWORD *)(*(_QWORD *)(v21 + 112) + 168LL),
        *(_DWORD *)(v21 + 140),
        *(_DWORD *)(v21 + 144),
        *(_DWORD *)(v21 + 148),
        *(_DWORD *)(v21 + 152));
      Rdp::Avenc::CFcWireEncoder::Flush(v17, v23);
    }
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v5 = 0;
    }
    v24 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v25 = GetCurrentThreadId();
      LOBYTE(v26) = v24;
      LOBYTE(v27) = v5;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v27,
        v26,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        (int)v30,
        (int)v32,
        11,
        &WPP_dce8caabb58138b44d6f1d43a0cfbbf0_Traceguids,
        v25);
    }
    if ( v16 )
    {
      if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
        if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
      }
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x68,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterframeprocessor.cpp",
                           v15);
  }
  return result;
}

```

## disassembly

```asm
0x180038380  push    rbx
0x180038382  push    rsi
0x180038383  push    rdi
0x180038384  push    r12
0x180038386  push    r13
0x180038388  push    r14
0x18003838a  push    r15
0x18003838c  sub     rsp, 90h
0x180038393  mov     r15, rcx
0x180038396  xor     r13d, r13d
0x180038399  lea     rcx, WPP_GLOBAL_Control
0x1800383a0  mov     rax, cs:WPP_GLOBAL_Control
0x1800383a7  lea     edi, [r13+1]
0x1800383ab  cmp     rax, rcx
0x1800383ae  jz      short loc_1800383BF
0x1800383b0  test    [rax+1Ch], dil
0x1800383b4  jz      short loc_1800383BF
0x1800383b6  cmp     byte ptr [rax+19h], 4
0x1800383ba  mov     bl, dil
0x1800383bd  jnb     short loc_1800383C2
0x1800383bf  mov     bl, r13b
0x1800383c2  lea     rax, WPP_RECORDER_INITIALIZED
0x1800383c9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800383d0  setnz   sil
0x1800383d4  test    bl, bl
0x1800383d6  jnz     short loc_1800383E6
0x1800383d8  test    sil, sil
0x1800383db  jnz     short loc_1800383E6
0x1800383dd  lea     r12, WPP_dce8caabb58138b44d6f1d43a0cfbbf0_Traceguids
0x1800383e4  jmp     short loc_18003841C
0x1800383e6  call    cs:__imp_GetCurrentThreadId
0x1800383ec  mov     dword ptr [rsp+0C8h+var_88], eax; char
0x1800383f0  lea     r12, WPP_dce8caabb58138b44d6f1d43a0cfbbf0_Traceguids
0x1800383f7  mov     [rsp+0C8h+MessageGuid], r12; MessageGuid
0x1800383fc  mov     [rsp+0C8h+var_98], 0Ah; __int16
0x180038403  mov     rcx, cs:WPP_GLOBAL_Control
0x18003840a  mov     r9, [rcx+28h]; int
0x18003840e  mov     r8b, sil; int
0x180038411  mov     dl, bl; int
0x180038413  mov     rcx, [rcx+10h]; int
0x180038417  call    WPP_RECORDER_AND_TRACE_SF_D
0x18003841c  mov     eax, cs:dword_1800C1058
0x180038422  cmp     eax, 4
0x180038425  jbe     loc_18003851A
0x18003842b  mov     rcx, cs:qword_1800C1070
0x180038432  mov     rax, cs:qword_1800C1068
0x180038439  mov     rdx, 470000000000h
0x180038443  test    rdx, rax
0x180038446  jz      loc_18003851A
0x18003844c  mov     rax, rcx
0x18003844f  and     rax, rdx
0x180038452  cmp     rax, rcx
0x180038455  jnz     loc_18003851A
0x18003845b  mov     rdx, [r15+18h]
0x18003845f  mov     rax, [rdx+70h]
0x180038463  mov     ecx, [rax+0A0h]
0x180038469  mov     [rsp+0C8h+arg_8], ecx
0x180038470  lea     rax, [rdx+78h]
0x180038474  mov     [rsp+0C8h+arg_10], rax
0x18003847c  lea     rax, aStartSinkwrite; "Start SinkWriter frame processor"
0x180038483  mov     [rsp+0C8h+arg_18], rax
0x18003848b  lea     rax, xmmword_1800C21A0
0x180038492  mov     [rsp+0C8h+var_68], rax
0x180038497  lea     rax, aRdpavenc; "RdpAvenc"
0x18003849e  mov     [rsp+0C8h+var_60], rax
0x1800384a3  mov     [rsp+0C8h+var_58], 1000000h
0x1800384ac  lea     rax, aCheckpoint; "Checkpoint"
0x1800384b3  mov     [rsp+0C8h+var_50], rax
0x1800384b8  lea     rax, [rsp+0C8h+arg_8]
0x1800384c0  mov     [rsp+0C8h+var_78], rax
0x1800384c5  lea     rax, [rsp+0C8h+arg_10]
0x1800384cd  mov     [rsp+0C8h+var_80], rax
0x1800384d2  lea     rax, [rsp+0C8h+arg_18]
0x1800384da  mov     qword ptr [rsp+0C8h+var_88], rax
0x1800384df  lea     rax, [rsp+0C8h+var_68]
0x1800384e4  mov     [rsp+0C8h+MessageGuid], rax
0x1800384e9  lea     rax, [rsp+0C8h+var_60]
0x1800384ee  mov     qword ptr [rsp+0C8h+var_98], rax
0x1800384f3  lea     rax, [rsp+0C8h+var_58]
0x1800384f8  mov     qword ptr [rsp+0C8h+var_A0], rax
0x1800384fd  lea     rax, [rsp+0C8h+var_50]
0x180038502  mov     qword ptr [rsp+0C8h+var_A8], rax
0x180038507  lea     rdx, byte_1800AF47F
0x18003850e  lea     rcx, dword_1800C1058
0x180038515  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U3@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@35AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x18003851a  mov     [rsp+0C8h+var_A8], 3Fh ; '?'; unsigned int
0x180038522  lea     r9, aOnecoreuapTerm_10; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180038529  lea     r8, aRdpAvencSinkwr_6; "Rdp::Avenc::SinkWriter::CSinkWriterFram"...
0x180038530  lea     rdx, aSinkwriterfram_0; "SinkWriterFrameProcessorStart"
0x180038537  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18003853e  call    ?push0@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1I@Z; Rdp::Modern::Utils::CInflightRecorder::push0(ushort const *,char const *,char const *,uint)
0x180038543  mov     rax, [r15+18h]
0x180038547  mov     r14, [rax+70h]
0x18003854b  add     r14, 120h
0x180038552  mov     rcx, [rsp+0C8h]
0x18003855a  lea     rax, aGraphicsFileIO; "Graphics file I/O channel is not availa"...
0x180038561  mov     qword ptr [rsp+0C8h+var_A0], rax
0x180038566  mov     qword ptr [rsp+0C8h+var_A8], r14
0x18003856b  mov     r9d, 80004003h
0x180038571  lea     r8, aOnecoreuapTerm_10; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180038578  mov     edx, 42h ; 'B'
0x18003857d  call    ??$Throw_HrIfNullMsg@V?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@wil@@$0A@@in1diag3@details@wil@@YAXPEAXIPEBDJAEBV?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@2@1ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(void *,uint,char const *,long,wil::com_ptr_t<IPropertyStore,wil::err_exception_policy> const &,char const *,...)
0x180038582  mov     r14, [r14]
0x180038585  mov     ecx, 70h ; 'p'; Size
0x18003858a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003858f  mov     rsi, rax
0x180038592  mov     [rax+8], edi
0x180038595  mov     [rax+0Ch], edi
0x180038598  lea     rax, ??_7?$_Ref_count_obj2@V?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@@std@@6B@; const std::_Ref_count_obj2<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>>::`vftable'
0x18003859f  mov     [rsi], rax
0x1800385a2  lea     rbx, [rsi+10h]
0x1800385a6  lea     rax, ??_7?$CRdpCtrl_Src@VCFcWireEncoder@Avenc@Rdp@@@Protocol@Rdp@@6B@; const Rdp::Protocol::CRdpCtrl_Src<Rdp::Avenc::CFcWireEncoder>::`vftable'
0x1800385ad  mov     [rbx], rax
0x1800385b0  mov     [rbx+8], r14
0x1800385b4  test    r14, r14
0x1800385b7  jz      short loc_1800385C9
0x1800385b9  mov     rax, [r14]
0x1800385bc  mov     rcx, r14
0x1800385bf  mov     rax, [rax+8]
0x1800385c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800385c8  nop
0x1800385c9  mov     [rbx+10h], r13
0x1800385cd  mov     [rbx+18h], r13
0x1800385d1  mov     [rbx+20h], r13
0x1800385d5  mov     [rbx+28h], r13
0x1800385d9  mov     [rbx+30h], r13
0x1800385dd  mov     [rbx+38h], r13
0x1800385e1  mov     [rbx+40h], r13
0x1800385e5  mov     [rbx+48h], r13
0x1800385e9  mov     [rbx+50h], r13
0x1800385ed  lea     rax, ??_7?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@6B@; const Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>::`vftable'
0x1800385f4  mov     [rbx], rax
0x1800385f7  mov     [rbx+58h], r13d
0x1800385fb  mov     [rsp+0C8h+var_50], rbx
0x180038600  mov     [rsp+0C8h+var_48], rsi
0x180038608  lea     rcx, [r15+20h]
0x18003860c  lea     rdx, [rsp+0C8h+var_50]
0x180038611  call    ?store@?$atomic@V?$shared_ptr@V?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@@std@@@std@@QEAAXV?$shared_ptr@V?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@@2@W4memory_order@2@@Z; std::atomic<std::shared_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>>>::store(std::shared_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>>,std::memory_order)
0x180038616  lea     r14, [r15+28h]
0x18003861a  mov     rcx, r14; Address
0x18003861d  call    ?_Lock_and_load@?$_Locked_pointer@V_Ref_count_base@std@@@std@@QEAAPEAV_Ref_count_base@2@XZ; std::_Locked_pointer<std::_Ref_count_base>::_Lock_and_load(void)
0x180038622  mov     rbx, rax
0x180038625  mov     rsi, [r15+20h]
0x180038629  mov     [rsp+0C8h+var_50], rsi
0x18003862e  mov     [rsp+0C8h+var_48], rax
0x180038636  test    rax, rax
0x180038639  jz      short loc_18003863F
0x18003863b  lock add [rax+8], edi
0x18003863f  mov     rdx, rbx
0x180038642  xchg    rdx, [r14]
0x180038645  and     dl, 3
0x180038648  cmp     dl, 2
0x18003864b  jnz     short loc_180038657
0x18003864d  mov     rcx, r14; Address
0x180038650  call    cs:__imp_WakeByAddressAll
0x180038656  nop
0x180038657  test    rsi, rsi
0x18003865a  jz      loc_180038769
0x180038660  xor     r9d, r9d; unsigned __int64
0x180038663  xor     r8d, r8d; unsigned int
0x180038666  mov     edx, 1000h; unsigned __int64
0x18003866b  mov     rcx, rsi; this
0x18003866e  call    ?AllocatePool@CFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@QEAAX_KI0@Z; Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::AllocatePool(unsigned __int64,uint,unsigned __int64)
0x180038673  mov     rax, [r15+18h]
0x180038677  mov     r13d, [rax+98h]
0x18003867e  mov     ecx, [rax+94h]
0x180038684  mov     dword ptr [rsp+0C8h+arg_10], ecx
0x18003868b  mov     eax, [rax+88h]
0x180038691  mov     [rsp+0C8h+arg_8], eax
0x180038698  mov     edx, 0Fh; unsigned __int64
0x18003869d  mov     rcx, rsi; this
0x1800386a0  call    ?EnsureBuffer@CFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@QEAAPEAX_K@Z; Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::EnsureBuffer(unsigned __int64)
0x1800386a5  mov     r14, rax
0x1800386a8  mov     rcx, [rsp+0C8h]
0x1800386b0  lea     rax, aUnableToEnsure_2; "Unable to ensure RDPGFX_CREATE_SURFACE_"...
0x1800386b7  mov     qword ptr [rsp+0C8h+var_A0], rax
0x1800386bc  mov     qword ptr [rsp+0C8h+var_A8], r14
0x1800386c1  mov     r9d, 8007000Eh
0x1800386c7  lea     r8, aOnecoreuapTerm_14; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x1800386ce  mov     edx, 10Ah
0x1800386d3  call    ??$Throw_HrIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBDJ01ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(void *,uint,char const *,long,void *,char const *,...)
0x1800386d8  mov     dword ptr [r14], 9
0x1800386df  mov     dword ptr [r14+4], 0Fh
0x1800386e7  mov     eax, [rsp+0C8h+arg_8]
0x1800386ee  mov     [r14+8], ax
0x1800386f3  mov     eax, dword ptr [rsp+0C8h+arg_10]
0x1800386fa  mov     [r14+0Ah], ax
0x1800386ff  mov     [r14+0Ch], r13w
0x180038704  mov     byte ptr [r14+0Eh], 21h ; '!'
0x180038709  mov     r8, [r15+18h]
0x18003870d  mov     r9, [r8+70h]
0x180038711  mov     eax, [r8+98h]
0x180038718  mov     dword ptr [rsp+0C8h+var_88], eax
0x18003871c  mov     eax, [r8+94h]
0x180038723  mov     dword ptr [rsp+0C8h+MessageGuid], eax
0x180038727  mov     eax, [r8+90h]
0x18003872e  mov     dword ptr [rsp+0C8h+var_98], eax
0x180038732  mov     eax, [r8+8Ch]
0x180038739  mov     [rsp+0C8h+var_A0], eax; int
0x18003873d  mov     eax, [r9+0A8h]
0x180038744  mov     [rsp+0C8h+var_A8], eax; int
0x180038748  mov     r9d, [r9+0A4h]
0x18003874f  mov     r8d, [r8+88h]
0x180038756  mov     rcx, rsi
0x180038759  call    ?MapSurfaceToScaledOutput@?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@QEAAX_NIHHHHII@Z; Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>::MapSurfaceToScaledOutput(bool,uint,int,int,int,int,uint,uint)
0x18003875e  mov     rcx, rsi; this
0x180038761  call    ?Flush@CFcWireEncoder@Avenc@Rdp@@QEAAXI@Z; Rdp::Avenc::CFcWireEncoder::Flush(uint)
0x180038766  xor     r13d, r13d
0x180038769  mov     rax, cs:WPP_GLOBAL_Control
0x180038770  lea     rcx, WPP_GLOBAL_Control
0x180038777  cmp     rax, rcx
0x18003877a  jz      short loc_180038788
0x18003877c  test    [rax+1Ch], dil
0x180038780  jz      short loc_180038788
0x180038782  cmp     byte ptr [rax+19h], 4
0x180038786  jnb     short loc_18003878B
0x180038788  mov     dil, r13b
0x18003878b  lea     rax, WPP_RECORDER_INITIALIZED
0x180038792  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180038799  setnz   sil
0x18003879d  test    dil, dil
0x1800387a0  jnz     short loc_1800387A7
0x1800387a2  test    sil, sil
0x1800387a5  jz      short loc_1800387D8
0x1800387a7  call    cs:__imp_GetCurrentThreadId
0x1800387ad  mov     dword ptr [rsp+0C8h+var_88], eax; char
0x1800387b1  mov     [rsp+0C8h+MessageGuid], r12; MessageGuid
0x1800387b6  mov     [rsp+0C8h+var_98], 0Bh; __int16
0x1800387bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800387c4  mov     r9, [rcx+28h]; int
0x1800387c8  mov     r8b, sil; int
0x1800387cb  mov     dl, dil; int
0x1800387ce  mov     rcx, [rcx+10h]; int
0x1800387d2  call    WPP_RECORDER_AND_TRACE_SF_D
0x1800387d7  nop
0x1800387d8  test    rbx, rbx
0x1800387db  jz      short loc_180038813
0x1800387dd  or      edi, 0FFFFFFFFh
0x1800387e0  mov     eax, edi
0x1800387e2  lock xadd [rbx+8], eax
0x1800387e7  add     eax, edi
0x1800387e9  jnz     short loc_180038813
0x1800387eb  mov     rax, [rbx]
0x1800387ee  mov     rcx, rbx
0x1800387f1  mov     rax, [rax]
0x1800387f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800387f9  mov     eax, edi
0x1800387fb  lock xadd [rbx+0Ch], eax
0x180038800  add     eax, edi
0x180038802  jnz     short loc_180038813
0x180038804  mov     rax, [rbx]
0x180038807  mov     rcx, rbx
0x18003880a  mov     rax, [rax+8]
0x18003880e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038813  xor     eax, eax
0x180038815  jmp     short loc_18003881E
0x180038817  mov     eax, [rsp+0C8h+arg_8]
0x18003881e  add     rsp, 90h
0x180038825  pop     r15
0x180038827  pop     r14
0x180038829  pop     r13
0x18003882b  pop     r12
0x18003882d  pop     rdi
0x18003882e  pop     rsi
0x18003882f  pop     rbx
0x180038830  retn
```
