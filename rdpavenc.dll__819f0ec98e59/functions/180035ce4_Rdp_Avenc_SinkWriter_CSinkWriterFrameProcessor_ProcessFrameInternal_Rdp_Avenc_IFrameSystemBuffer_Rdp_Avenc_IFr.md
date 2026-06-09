# Rdp::Avenc::SinkWriter::CSinkWriterFrameProcessor::ProcessFrameInternal<Rdp::Avenc::IFrameSystemBuffer>(Rdp::Avenc::IFrameSystemBuffer &,bool *)

- ea: `0x180035ce4`
- end: `0x18003629f`
- name: `??$ProcessFrameInternal@UIFrameSystemBuffer@Avenc@Rdp@@@CSinkWriterFrameProcessor@SinkWriter@Avenc@Rdp@@IEAAJAEAUIFrameSystemBuffer@23@PEA_N@Z`
- size: `1467`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180035240`

## callees

- `0x18000154c`
- `0x1800032cc`
- `0x180003418`
- `0x1800039dc`
- `0x18000a1b4`
- `0x18000ec04`
- `0x180026864`
- `0x18002b84c`
- `0x180035ce4`
- `0x18003670c`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-perfcounters-l1-1-0!PerfIncrementULongCounterValue` at `0x180035e86`
- `api-ms-win-core-perfcounters-l1-1-0!PerfIncrementULongCounterValue` at `0x180035e86`

## string_xrefs

- `0x18003628c`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180035ea3`: `onecoreuap\termsrv\rdp_bin\win\common/inc/PerfMon.h`
- `0x180035d23`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\sinkwriterprocessor\sinkwriterframeprocessor.cpp`
- `0x180035d94`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\sinkwriterprocessor\sinkwriterframeprocessor.cpp`
- `0x180035df9`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\sinkwriterprocessor\sinkwriterframeprocessor.cpp`
- `0x18003611e`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\sinkwriterprocessor\sinkwriterframeprocessor.cpp`
- `0x180035d7a`: `Rdp::Avenc::SinkWriter::CSinkWriterFrameProcessor::ProcessFrameInternal`
- `0x180035e00`: `Rdp::Avenc::SinkWriter::CSinkWriterFrameProcessor::ProcessFrameInternal`
- `0x180036125`: `Rdp::Avenc::SinkWriter::CSinkWriterFrameProcessor::ProcessFrameInternal`

## pseudocode

```c
__int64 __fastcall Rdp::Avenc::SinkWriter::CSinkWriterFrameProcessor::ProcessFrameInternal<Rdp::Avenc::IFrameSystemBuffer>(
        __int64 a1,
        __int64 a2,
        _BYTE *a3)
{
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
  int v19; // eax
  __int64 v20; // rdx
  int v21; // r8d
  int v22; // r9d
  int v23; // [rsp+20h] [rbp-F8h]
  int v24; // [rsp+20h] [rbp-F8h]
  const char *v25; // [rsp+28h] [rbp-F0h]
  struct Rdp::Avenc::IFrameBuffer1 *v26; // [rsp+90h] [rbp-88h] BYREF
  const char *v27; // [rsp+98h] [rbp-80h] BYREF
  const char *v28; // [rsp+A0h] [rbp-78h] BYREF
  const char *v29; // [rsp+A8h] [rbp-70h] BYREF
  const char *v30; // [rsp+B0h] [rbp-68h] BYREF
  const char *v31; // [rsp+B8h] [rbp-60h] BYREF
  _QWORD v32[11]; // [rsp+C0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]
  _BYTE *v34; // [rsp+130h] [rbp+18h] BYREF
  unsigned int v35; // [rsp+138h] [rbp+20h] BYREF

  v34 = a3;
  if ( a3 )
  {
    v35 = 0;
    if ( (unsigned int)dword_1800C1058 > 5 )
    {
      LODWORD(v27) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 120LL))(a2);
      v30 = "NewFrame";
      v29 = "Rdp::Avenc::SinkWriter::CSinkWriterFrameProcessor::ProcessFrameInternal";
      LODWORD(v26) = 205;
      v28 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterframeprocessor.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)&word_1800AF22E,
        v7,
        v8,
        (__int64)&v28,
        (__int64)&v26,
        (__int64)&v29,
        (__int64)&v30,
        (__int64)&v27);
    }
    v9 = (__int64 *)(a1 + 104);
    v32[0] = a1 + 104;
    v10 = *(_QWORD *)(*(_QWORD *)(a1 + 104) + 112LL);
    v11 = *(_QWORD *)(v10 + 320);
    if ( v11 )
      _InterlockedIncrement((volatile signed __int32 *)(v11 + 8));
    v28 = *(const char **)(v10 + 312);
    v32[1] = v28;
    v12 = *(volatile signed __int32 **)(v10 + 320);
    v32[2] = v12;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 40LL))(a2);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 56LL))(a2);
    v13 = PerfIncrementULongCounterValue(*(HANDLE *)v28, *((PPERF_COUNTERSET_INSTANCE *)v28 + 3), 1u, 1u);
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0x18B,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/PerfMon.h",
      (const char *)v13,
      (unsigned int)"PerfIncrementULongCounterValue failed",
      v25);
    if ( Rdp::Avenc::ClientFrameRateTracker::IsClientStalled(*(Rdp::Avenc::ClientFrameRateTracker **)(a1 + 136)) )
    {
      if ( (unsigned int)dword_1800C1058 > 4 )
      {
        LODWORD(v26) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 120LL))(a2);
        v28 = (const char *)(*v9 + 120);
        v29 = "Client stall detected. Skipping frame";
        v30 = "Rdp::Avenc::SinkWriter::CSinkWriterFrameProcessor::ProcessFrameInternal";
        LODWORD(v27) = 232;
        v31 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterframeprocessor.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1800C1058,
          (unsigned int)&dword_1800AF10C,
          v17,
          v18,
          (__int64)&v31,
          (__int64)&v27,
          (__int64)&v30,
          (__int64)&v29,
          (__int64)&v28,
          (__int64)&v26);
      }
    }
    else
    {
      v26 = 0;
      v16 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct Rdp::Avenc::IFrameBuffer1 **))a2)(
              a2,
              &GUID_5ce16a4c_4058_480b_8806_9c82986f8662,
              &v26);
      if ( v16 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x1CBE,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
          (const char *)(unsigned int)v16,
          v24);
      Rdp::Avenc::SinkWriter::CMFEncoder::EncodeFrame(*(Rdp::Avenc::SinkWriter::CMFEncoder **)(a1 + 128), v26, &v35);
      if ( v26 )
        (*(void (__fastcall **)(struct Rdp::Avenc::IFrameBuffer1 *))(*(_QWORD *)v26 + 16LL))(v26);
    }
    if ( (unsigned int)dword_1800C1058 > 5 )
    {
      v31 = *(const char **)(*(_QWORD *)(a1 + 136) + 136LL);
      v28 = (const char *)(*v9 + 120);
      v29 = "FrameRate";
      v30 = "Rdp::Avenc::SinkWriter::CSinkWriterFrameProcessor::ProcessFrameInternal";
      LODWORD(v26) = 237;
      v27 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterframeprocessor.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)&word_1800AF166,
        v14,
        v15,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v31);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 48LL))(a2);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 64LL))(a2);
    if ( v12 )
    {
      if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
        if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
      }
    }
    v19 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)a2 + 112LL))(a2, 1, v35, 0);
    if ( v19 < 0 && (unsigned int)dword_1800C1058 > 2 )
    {
      LODWORD(v34) = v19;
      v35 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 120LL))(a2);
      v20 = *v9;
      LODWORD(v26) = *(_DWORD *)(*(_QWORD *)(*v9 + 112) + 160LL);
      v32[0] = v20 + 120;
      v31 = "Failed to report frame statistics";
      v28 = "Rdp::Avenc::SinkWriter::CSinkWriterFrameProcessor::ProcessFrameInternal";
      LODWORD(v27) = 285;
      v29 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterframeprocessor.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)&dword_1800AF094,
        v21,
        v22,
        (__int64)&v29,
        (__int64)&v27,
        (__int64)&v28,
        (__int64)&v31,
        (__int64)v32,
        (__int64)&v26,
        (__int64)&v35,
        (__int64)&v34);
    }
    *a3 = 0;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC5,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterframeprocessor.cpp",
      (const char *)0x80004003LL,
      v23);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x180035ce4  mov     [rsp+arg_10], r8
0x180035ce9  mov     [rsp+arg_8], rdx
0x180035cee  mov     [rsp+arg_0], rcx
0x180035cf3  push    rbx
0x180035cf4  push    rsi
0x180035cf5  push    rdi
0x180035cf6  push    r12
0x180035cf8  push    r13
0x180035cfa  push    r14
0x180035cfc  push    r15
0x180035cfe  sub     rsp, 0E0h
0x180035d05  mov     r12, r8
0x180035d08  mov     rbx, rdx
0x180035d0b  mov     r14, rcx
0x180035d0e  test    r8, r8
0x180035d11  jnz     short loc_180035D3B
0x180035d13  mov     rcx, [rsp+118h]; this
0x180035d1b  mov     ebx, 80004003h
0x180035d20  mov     r9d, ebx; char *
0x180035d23  lea     r8, aOnecoreuapTerm_10; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180035d2a  mov     edx, 0C5h; void *
0x180035d2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035d34  mov     eax, ebx
0x180035d36  jmp     loc_180036276
0x180035d3b  mov     [rsp+118h+arg_18], 0
0x180035d46  mov     eax, cs:dword_1800C1058
0x180035d4c  cmp     eax, 5
0x180035d4f  jbe     loc_180035DF9
0x180035d55  mov     rax, [rdx]
0x180035d58  mov     rcx, rbx
0x180035d5b  mov     rax, [rax+78h]
0x180035d5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035d64  mov     dword ptr [rsp+118h+var_80], eax
0x180035d6b  lea     rax, aNewframe; "NewFrame"
0x180035d72  mov     [rsp+118h+var_68], rax
0x180035d7a  lea     r13, aRdpAvencSinkwr_5; "Rdp::Avenc::SinkWriter::CSinkWriterFram"...
0x180035d81  mov     [rsp+118h+var_70], r13
0x180035d89  mov     dword ptr [rsp+118h+var_88], 0CDh
0x180035d94  lea     rsi, aOnecoreuapTerm_10; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180035d9b  mov     [rsp+118h+var_78], rsi
0x180035da3  lea     rax, [rsp+118h+var_80]
0x180035dab  mov     [rsp+118h+var_D8], rax
0x180035db0  lea     rax, [rsp+118h+var_68]
0x180035db8  mov     [rsp+118h+var_E0], rax
0x180035dbd  lea     rax, [rsp+118h+var_70]
0x180035dc5  mov     [rsp+118h+var_E8], rax
0x180035dca  lea     rax, [rsp+118h+var_88]
0x180035dd2  mov     [rsp+118h+var_F0], rax
0x180035dd7  lea     rax, [rsp+118h+var_78]
0x180035ddf  mov     qword ptr [rsp+118h+var_F8], rax
0x180035de4  lea     rdx, word_1800AF22E
0x180035deb  lea     rcx, dword_1800C1058
0x180035df2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180035df7  jmp     short loc_180035E07
0x180035df9  lea     rsi, aOnecoreuapTerm_10; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180035e00  lea     r13, aRdpAvencSinkwr_5; "Rdp::Avenc::SinkWriter::CSinkWriterFram"...
0x180035e07  lea     r15, [r14+68h]
0x180035e0b  mov     [rsp+118h+var_58], r15
0x180035e13  mov     rax, [r15]
0x180035e16  mov     rdi, [rax+70h]
0x180035e1a  mov     rax, [rdi+140h]
0x180035e21  test    rax, rax
0x180035e24  jz      short loc_180035E2A
0x180035e26  lock inc dword ptr [rax+8]
0x180035e2a  mov     rax, [rdi+138h]
0x180035e31  mov     [rsp+118h+var_78], rax
0x180035e39  mov     [rsp+118h+var_50], rax
0x180035e41  mov     rdi, [rdi+140h]
0x180035e48  mov     [rsp+118h+var_48], rdi
0x180035e50  mov     rax, [rbx]
0x180035e53  mov     rcx, rbx
0x180035e56  mov     rax, [rax+28h]
0x180035e5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035e5f  mov     rax, [rbx]
0x180035e62  mov     rcx, rbx
0x180035e65  mov     rax, [rax+38h]
0x180035e69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035e6e  mov     r9d, 1; Value
0x180035e74  mov     r8d, r9d; CounterId
0x180035e77  mov     rcx, [rsp+118h+var_78]
0x180035e7f  mov     rdx, [rcx+18h]; Instance
0x180035e83  mov     rcx, [rcx]; Provider
0x180035e86  call    cs:__imp_PerfIncrementULongCounterValue
0x180035e8c  mov     rcx, [rsp+118h]; this
0x180035e94  lea     rdx, aPerfincrementu; "PerfIncrementULongCounterValue failed"
0x180035e9b  mov     qword ptr [rsp+118h+var_F8], rdx; int
0x180035ea0  mov     r9d, eax; char *
0x180035ea3  lea     r8, aOnecoreuapTerm_29; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x180035eaa  mov     edx, 18Bh; void *
0x180035eaf  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180035eb4  mov     rcx, [r14+88h]; this
0x180035ebb  call    ?IsClientStalled@ClientFrameRateTracker@Avenc@Rdp@@QEAA_NXZ; Rdp::Avenc::ClientFrameRateTracker::IsClientStalled(void)
0x180035ec0  test    al, al
0x180035ec2  jnz     short loc_180035F39
0x180035ec4  mov     [rsp+118h+var_88], 0
0x180035ed0  mov     rax, [rbx]
0x180035ed3  lea     r8, [rsp+118h+var_88]
0x180035edb  lea     rdx, _GUID_5ce16a4c_4058_480b_8806_9c82986f8662
0x180035ee2  mov     rcx, rbx
0x180035ee5  mov     rax, [rax]
0x180035ee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035eed  mov     rcx, [rsp+118h]; this
0x180035ef5  test    eax, eax
0x180035ef7  js      loc_180036289
0x180035efd  lea     r8, [rsp+118h+arg_18]; unsigned int *
0x180035f05  mov     rdx, [rsp+118h+var_88]; struct Rdp::Avenc::IFrameBuffer1 *
0x180035f0d  mov     rcx, [r14+80h]; this
0x180035f14  call    ?EncodeFrame@CMFEncoder@SinkWriter@Avenc@Rdp@@QEAAXPEAUIFrameBuffer1@34@AEAI@Z; Rdp::Avenc::SinkWriter::CMFEncoder::EncodeFrame(Rdp::Avenc::IFrameBuffer1 *,uint &)
0x180035f19  nop
0x180035f1a  mov     rcx, [rsp+118h+var_88]
0x180035f22  test    rcx, rcx
0x180035f25  jz      short loc_180035F34
0x180035f27  mov     rax, [rcx]
0x180035f2a  mov     rax, [rax+10h]
0x180035f2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035f33  nop
0x180035f34  jmp     loc_180035FF8
0x180035f39  mov     eax, cs:dword_1800C1058
0x180035f3f  cmp     eax, 4
0x180035f42  jbe     loc_180035FF8
0x180035f48  mov     rax, [rbx]
0x180035f4b  mov     rcx, rbx
0x180035f4e  mov     rax, [rax+78h]
0x180035f52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035f57  mov     dword ptr [rsp+118h+var_88], eax
0x180035f5e  mov     rax, [r15]
0x180035f61  add     rax, 78h ; 'x'
0x180035f65  mov     [rsp+118h+var_78], rax
0x180035f6d  lea     rax, aClientStallDet; "Client stall detected. Skipping frame"
0x180035f74  mov     [rsp+118h+var_70], rax
0x180035f7c  mov     [rsp+118h+var_68], r13
0x180035f84  mov     dword ptr [rsp+118h+var_80], 0E8h
0x180035f8f  mov     [rsp+118h+var_60], rsi
0x180035f97  lea     rax, [rsp+118h+var_88]
0x180035f9f  mov     [rsp+118h+var_D0], rax
0x180035fa4  lea     rax, [rsp+118h+var_78]
0x180035fac  mov     [rsp+118h+var_D8], rax
0x180035fb1  lea     rax, [rsp+118h+var_70]
0x180035fb9  mov     [rsp+118h+var_E0], rax
0x180035fbe  lea     rax, [rsp+118h+var_68]
0x180035fc6  mov     [rsp+118h+var_E8], rax
0x180035fcb  lea     rax, [rsp+118h+var_80]
0x180035fd3  mov     [rsp+118h+var_F0], rax
0x180035fd8  lea     rax, [rsp+118h+var_60]
0x180035fe0  mov     qword ptr [rsp+118h+var_F8], rax
0x180035fe5  lea     rdx, dword_1800AF10C
0x180035fec  lea     rcx, dword_1800C1058
0x180035ff3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByRef@$0BA@@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByRef@$0BA@@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x180035ff8  mov     eax, cs:dword_1800C1058
0x180035ffe  cmp     eax, 5
0x180036001  jbe     loc_1800360B9
0x180036007  mov     rax, [r14+88h]
0x18003600e  movsd   xmm0, qword ptr [rax+88h]
0x180036016  movsd   [rsp+118h+var_60], xmm0
0x18003601f  mov     rax, [r15]
0x180036022  add     rax, 78h ; 'x'
0x180036026  mov     [rsp+118h+var_78], rax
0x18003602e  lea     rax, aFramerate; "FrameRate"
0x180036035  mov     [rsp+118h+var_70], rax
0x18003603d  mov     [rsp+118h+var_68], r13
0x180036045  mov     dword ptr [rsp+118h+var_88], 0EDh
0x180036050  mov     [rsp+118h+var_80], rsi
0x180036058  lea     rax, [rsp+118h+var_60]
0x180036060  mov     [rsp+118h+var_D0], rax
0x180036065  lea     rax, [rsp+118h+var_78]
0x18003606d  mov     [rsp+118h+var_D8], rax
0x180036072  lea     rax, [rsp+118h+var_70]
0x18003607a  mov     [rsp+118h+var_E0], rax
0x18003607f  lea     rax, [rsp+118h+var_68]
0x180036087  mov     [rsp+118h+var_E8], rax
0x18003608c  lea     rax, [rsp+118h+var_88]
0x180036094  mov     [rsp+118h+var_F0], rax
0x180036099  lea     rax, [rsp+118h+var_80]
0x1800360a1  mov     qword ptr [rsp+118h+var_F8], rax
0x1800360a6  lea     rdx, word_1800AF166
0x1800360ad  lea     rcx, dword_1800C1058
0x1800360b4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &)
0x1800360b9  mov     rax, [rbx]
0x1800360bc  mov     rcx, rbx
0x1800360bf  mov     rax, [rax+30h]
0x1800360c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800360c8  mov     rax, [rbx]
0x1800360cb  mov     rcx, rbx
0x1800360ce  mov     rax, [rax+40h]
0x1800360d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800360d7  mov     r14d, 1
0x1800360dd  test    rdi, rdi
0x1800360e0  jz      short loc_18003611A
0x1800360e2  or      eax, 0FFFFFFFFh
0x1800360e5  lock xadd [rdi+8], eax
0x1800360ea  cmp     eax, r14d
0x1800360ed  jnz     short loc_18003611A
0x1800360ef  mov     rax, [rdi]
0x1800360f2  mov     rcx, rdi
0x1800360f5  mov     rax, [rax]
0x1800360f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800360fd  or      eax, 0FFFFFFFFh
0x180036100  lock xadd [rdi+0Ch], eax
0x180036105  cmp     eax, r14d
0x180036108  jnz     short loc_18003611A
0x18003610a  mov     rax, [rdi]
0x18003610d  mov     rcx, rdi
0x180036110  mov     rax, [rax+8]
0x180036114  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036119  nop
0x18003611a  xor     edi, edi
0x18003611c  jmp     short loc_180036153
0x18003611e  lea     rsi, aOnecoreuapTerm_10; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180036125  lea     r13, aRdpAvencSinkwr_5; "Rdp::Avenc::SinkWriter::CSinkWriterFram"...
0x18003612c  mov     r12, [rsp+118h+arg_10]
0x180036134  mov     rbx, [rsp+118h+arg_8]
0x18003613c  mov     r14d, dword ptr [rsp+118h+var_88]
0x180036144  mov     edi, dword ptr [rsp+118h+var_80]
0x18003614b  mov     r15, [rsp+118h+var_58]
0x180036153  mov     rax, [rbx]
0x180036156  xor     r9d, r9d
0x180036159  mov     r8d, [rsp+118h+arg_18]
0x180036161  mov     edx, r14d
0x180036164  mov     rcx, rbx
0x180036167  mov     rax, [rax+70h]
0x18003616b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036170  test    eax, eax
0x180036172  jns     loc_180036269
0x180036178  mov     ecx, cs:dword_1800C1058
0x18003617e  cmp     ecx, 2
0x180036181  jbe     loc_180036269
0x180036187  mov     dword ptr [rsp+118h+arg_10], eax
0x18003618e  mov     rax, [rbx]
0x180036191  mov     rcx, rbx
0x180036194  mov     rax, [rax+78h]
0x180036198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003619d  mov     [rsp+118h+arg_18], eax
0x1800361a4  mov     rdx, [r15]
0x1800361a7  mov     rax, [rdx+70h]
0x1800361ab  mov     ecx, [rax+0A0h]
0x1800361b1  mov     dword ptr [rsp+118h+var_88], ecx
0x1800361b8  lea     rax, [rdx+78h]
0x1800361bc  mov     [rsp+118h+var_58], rax
0x1800361c4  lea     rax, aFailedToReport; "Failed to report frame statistics"
0x1800361cb  mov     [rsp+118h+var_60], rax
0x1800361d3  mov     [rsp+118h+var_78], r13
0x1800361db  mov     dword ptr [rsp+118h+var_80], 11Dh
0x1800361e6  mov     [rsp+118h+var_70], rsi
0x1800361ee  lea     rax, [rsp+118h+arg_10]
0x1800361f6  mov     [rsp+118h+var_C0], rax
0x1800361fb  lea     rax, [rsp+118h+arg_18]
0x180036203  mov     [rsp+118h+var_C8], rax
0x180036208  lea     rax, [rsp+118h+var_88]
0x180036210  mov     [rsp+118h+var_D0], rax
0x180036215  lea     rax, [rsp+118h+var_58]
0x18003621d  mov     [rsp+118h+var_D8], rax
0x180036222  lea     rax, [rsp+118h+var_60]
0x18003622a  mov     [rsp+118h+var_E0], rax
0x18003622f  lea     rax, [rsp+118h+var_78]
0x180036237  mov     [rsp+118h+var_E8], rax
0x18003623c  lea     rax, [rsp+118h+var_80]
0x180036244  mov     [rsp+118h+var_F0], rax
0x180036249  lea     rax, [rsp+118h+var_70]
0x180036251  mov     qword ptr [rsp+118h+var_F8], rax
0x180036256  lea     rdx, dword_1800AF094
0x18003625d  lea     rcx, dword_1800C1058
0x180036264  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByRef@$0BA@@@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByRef@$0BA@@@444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180036269  cmp     r14d, 1
0x18003626d  setnz   cl
0x180036270  mov     [r12], cl
0x180036274  mov     eax, edi
0x180036276  add     rsp, 0E0h
0x18003627d  pop     r15
0x18003627f  pop     r14
0x180036281  pop     r13
0x180036283  pop     r12
0x180036285  pop     rdi
0x180036286  pop     rsi
0x180036287  pop     rbx
0x180036288  retn
0x180036289  mov     r9d, eax; char *
0x18003628c  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180036293  mov     edx, 1CBEh; void *
0x180036298  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
