# Rdp::Avenc::SinkWriter::CSinkWriterFrameProcessor::Stop(void)

- ea: `0x180038980`
- end: `0x180038e03`
- name: `?Stop@CSinkWriterFrameProcessor@SinkWriter@Avenc@Rdp@@UEAAJXZ`
- size: `1155`
- prototype: `__int64 __fastcall(Rdp::Avenc::SinkWriter::CSinkWriterFrameProcessor *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180035710`

## callees

- `0x180002be0`
- `0x18001143c`
- `0x1800153f8`
- `0x180015480`
- `0x180022fb8`
- `0x180023b34`
- `0x180023ee4`
- `0x18002dd40`
- `0x18002e0c4`
- `0x180038838`
- `0x180038980`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800389e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180038d78`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800389e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180038d78`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180038c56`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180038c56`

## string_xrefs

- `0x180038cd7`: `onecoreuap\termsrv\rdp_bin\win\common/protocol/RdpEgfx/RdpEgfx.h`
- `0x180038cc0`: `Unable to ensure RDPGFX_DELETE_SURFACE_PDU_SIZE`
- `0x180038bc5`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\sinkwriterprocessor\sinkwriterframeprocessor.cpp`
- `0x180038a7a`: `Stop SinkWriter frame processor`
- `0x180038bd3`: `SinkWriterFrameProcessorStop: Id {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}`
- `0x180038bcc`: `Rdp::Avenc::SinkWriter::CSinkWriterFrameProcessor::Stop`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Rdp::Avenc::SinkWriter::CSinkWriterFrameProcessor::Stop(
        Rdp::Avenc::SinkWriter::CSinkWriterFrameProcessor *this,
        __int64 a2,
        int a3,
        int a4)
{
  char v5; // r12
  bool v6; // bl
  bool v7; // di
  char CurrentThreadId; // al
  int v9; // r8d
  int v10; // edx
  __int64 v11; // rcx
  __int64 v12; // r14
  Rdp::Avenc::SinkWriter::CMFEncoder *v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rax
  volatile signed __int32 *v16; // rbx
  Rdp::Avenc::CFcWireEncoderWithBulkUncompressed *v17; // rsi
  const char *v18; // r9
  int v19; // r13d
  _DWORD *v20; // rdi
  unsigned int v21; // edx
  __int64 *v22; // r14
  __int64 v23; // rcx
  bool v24; // di
  char v25; // al
  int v26; // r8d
  int v27; // edx
  __int64 result; // rax
  int v29; // [rsp+20h] [rbp-C8h]
  int v30; // [rsp+20h] [rbp-C8h]
  int v31; // [rsp+28h] [rbp-C0h]
  int v32; // [rsp+28h] [rbp-C0h]
  const char *v33; // [rsp+80h] [rbp-68h] BYREF
  __int128 v34; // [rsp+88h] [rbp-60h] BYREF
  _QWORD v35[10]; // [rsp+98h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]
  char *v37; // [rsp+F0h] [rbp+8h] BYREF
  volatile signed __int32 *v38; // [rsp+F8h] [rbp+10h] BYREF
  const char *v39; // [rsp+100h] [rbp+18h] BYREF
  int *v40; // [rsp+108h] [rbp+20h] BYREF

  v5 = 1;
  v6 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
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
      12,
      &WPP_dce8caabb58138b44d6f1d43a0cfbbf0_Traceguids,
      CurrentThreadId);
  }
  if ( (unsigned int)dword_1800C1058 > 4
    && (qword_1800C1068 & 0x470000000000LL) != 0
    && (qword_1800C1070 & 0x470000000000LL) == qword_1800C1070 )
  {
    v11 = *((_QWORD *)this + 3);
    v38 = (volatile signed __int32 *)(v11 + 120);
    LODWORD(v37) = *(_DWORD *)(*(_QWORD *)(v11 + 112) + 160LL);
    v39 = "Stop SinkWriter frame processor";
    v40 = &xmmword_1800C21A0;
    v33 = "RdpAvenc";
    *(_QWORD *)&v34 = 0x1000000;
    v35[0] = "Checkpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
      (unsigned int)&dword_1800C1058,
      (unsigned int)&dword_1800AF414,
      a3,
      a4,
      (__int64)v35,
      (__int64)&v34,
      (__int64)&v33,
      (__int64)&v40,
      (__int64)&v39,
      (__int64)&v37,
      (__int64)&v38);
  }
  v37 = (char *)this + 24;
  v12 = *((_QWORD *)this + 3);
  v32 = *(_DWORD *)(v12 + 120);
  try
  {
    Rdp::Modern::Utils::CInflightRecorder::pushN(
      (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      (wchar_t *)L"SinkWriterFrameProcessorStop: Id {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}",
      "Rdp::Avenc::SinkWriter::CSinkWriterFrameProcessor::Stop",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterframeprocessor.cpp",
      0x8Au);
    v13 = (Rdp::Avenc::SinkWriter::CMFEncoder *)*((_QWORD *)this + 6);
    if ( v13 )
    {
      Rdp::Avenc::SinkWriter::CMFEncoder::Stop(v13);
      v14 = *((_QWORD *)this + 6);
      *((_QWORD *)this + 6) = 0;
      if ( v14 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v14 + 24LL))(v14, 1);
    }
    v15 = std::_Locked_pointer<std::_Ref_count_base>::_Lock_and_load((char *)this + 40);
    v16 = (volatile signed __int32 *)v15;
    v38 = (volatile signed __int32 *)v15;
    v17 = (Rdp::Avenc::CFcWireEncoderWithBulkUncompressed *)*((_QWORD *)this + 4);
    v35[0] = v17;
    v35[1] = v15;
    if ( v15 )
      _InterlockedAdd((volatile signed __int32 *)(v15 + 8), 1u);
    if ( (_InterlockedExchange64((volatile __int64 *)this + 5, v15) & 3) == 2 )
      WakeByAddressAll((char *)this + 40);
    v34 = 0;
    std::atomic<std::shared_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>>>::store(
      (char *)this + 32,
      &v34);
    if ( v17 )
    {
      try
      {
        Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::AllocatePool(v17, 0x1000u, 0, 0);
        v22 = (__int64 *)v37;
        v19 = *(_DWORD *)(*(_QWORD *)v37 + 136LL);
        v20 = Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::EnsureBuffer(v17, 0xAu);
        wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(
          retaddr,
          343,
          "onecoreuap\\termsrv\\rdp_bin\\win\\common/protocol/RdpEgfx/RdpEgfx.h",
          2147942414LL,
          v20,
          "Unable to ensure RDPGFX_DELETE_SURFACE_PDU_SIZE");
        *v20 = 10;
        v20[1] = 10;
        *((_WORD *)v20 + 4) = v19;
        Rdp::Avenc::CFcWireEncoder::Flush(v17, v21);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0xA2,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterframeprocessor.cpp",
          v18);
        v5 = 1;
        v16 = v38;
        goto LABEL_22;
      }
    }
    else
    {
LABEL_22:
      v22 = (__int64 *)v37;
    }
    v23 = *v22;
    *v22 = 0;
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
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
        v30,
        v32,
        13,
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
                           (void *)0xAA,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterframeprocessor.cpp",
                           v18);
  }
  return result;
}

```

## disassembly

```asm
0x180038980  push    rbx
0x180038982  push    rsi
0x180038983  push    rdi
0x180038984  push    r12
0x180038986  push    r13
0x180038988  push    r14
0x18003898a  push    r15
0x18003898c  sub     rsp, 0B0h
0x180038993  mov     r13, rcx
0x180038996  lea     rcx, WPP_GLOBAL_Control
0x18003899d  mov     rax, cs:WPP_GLOBAL_Control
0x1800389a4  mov     r12d, 1
0x1800389aa  cmp     rax, rcx
0x1800389ad  jz      short loc_1800389C3
0x1800389af  test    [rax+1Ch], r12b
0x1800389b3  jz      short loc_1800389C3
0x1800389b5  cmp     byte ptr [rax+19h], 4
0x1800389b9  jb      short loc_1800389C3
0x1800389bb  mov     bl, r12b
0x1800389be  xor     r15d, r15d
0x1800389c1  jmp     short loc_1800389C9
0x1800389c3  xor     r15d, r15d
0x1800389c6  mov     bl, r15b
0x1800389c9  lea     rax, WPP_RECORDER_INITIALIZED
0x1800389d0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800389d7  setnz   dil
0x1800389db  test    bl, bl
0x1800389dd  jnz     short loc_1800389E4
0x1800389df  test    dil, dil
0x1800389e2  jz      short loc_180038A1A
0x1800389e4  call    cs:__imp_GetCurrentThreadId
0x1800389ea  mov     dword ptr [rsp+0E8h+var_A8], eax; char
0x1800389ee  lea     rsi, WPP_dce8caabb58138b44d6f1d43a0cfbbf0_Traceguids
0x1800389f5  mov     [rsp+0E8h+MessageGuid], rsi; MessageGuid
0x1800389fa  mov     [rsp+0E8h+var_B8], 0Ch; __int16
0x180038a01  mov     rcx, cs:WPP_GLOBAL_Control
0x180038a08  mov     r9, [rcx+28h]; int
0x180038a0c  mov     r8b, dil; int
0x180038a0f  mov     dl, bl; int
0x180038a11  mov     rcx, [rcx+10h]; int
0x180038a15  call    WPP_RECORDER_AND_TRACE_SF_D
0x180038a1a  mov     eax, cs:dword_1800C1058
0x180038a20  cmp     eax, 4
0x180038a23  jbe     loc_180038B30
0x180038a29  mov     rcx, cs:qword_1800C1070
0x180038a30  mov     rax, cs:qword_1800C1068
0x180038a37  mov     rdx, 470000000000h
0x180038a41  test    rdx, rax
0x180038a44  jz      loc_180038B30
0x180038a4a  mov     rax, rcx
0x180038a4d  and     rax, rdx
0x180038a50  cmp     rax, rcx
0x180038a53  jnz     loc_180038B30
0x180038a59  mov     rcx, [r13+18h]
0x180038a5d  lea     rax, [rcx+78h]
0x180038a61  mov     [rsp+0E8h+arg_8], rax
0x180038a69  mov     rax, [rcx+70h]
0x180038a6d  mov     ecx, [rax+0A0h]
0x180038a73  mov     dword ptr [rsp+0E8h+arg_0], ecx
0x180038a7a  lea     rax, aStopSinkwriter; "Stop SinkWriter frame processor"
0x180038a81  mov     [rsp+0E8h+arg_10], rax
0x180038a89  lea     rax, xmmword_1800C21A0
0x180038a90  mov     [rsp+0E8h+arg_18], rax
0x180038a98  lea     rax, aRdpavenc; "RdpAvenc"
0x180038a9f  mov     [rsp+0E8h+var_68], rax
0x180038aa7  mov     qword ptr [rsp+0E8h+var_60], 1000000h
0x180038ab3  lea     rax, aCheckpoint; "Checkpoint"
0x180038aba  mov     [rsp+0E8h+var_50], rax
0x180038ac2  lea     rax, [rsp+0E8h+arg_8]
0x180038aca  mov     [rsp+0E8h+var_98], rax
0x180038acf  lea     rax, [rsp+0E8h+arg_0]
0x180038ad7  mov     [rsp+0E8h+var_A0], rax
0x180038adc  lea     rax, [rsp+0E8h+arg_10]
0x180038ae4  mov     qword ptr [rsp+0E8h+var_A8], rax
0x180038ae9  lea     rax, [rsp+0E8h+arg_18]
0x180038af1  mov     [rsp+0E8h+MessageGuid], rax
0x180038af6  lea     rax, [rsp+0E8h+var_68]
0x180038afe  mov     qword ptr [rsp+0E8h+var_B8], rax
0x180038b03  lea     rax, [rsp+0E8h+var_60]
0x180038b0b  mov     [rsp+0E8h+var_C0], rax
0x180038b10  lea     rax, [rsp+0E8h+var_50]
0x180038b18  mov     qword ptr [rsp+0E8h+var_C8], rax
0x180038b1d  lea     rdx, dword_1800AF414
0x180038b24  lea     rcx, dword_1800C1058
0x180038b2b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x180038b30  lea     rax, [r13+18h]
0x180038b34  mov     [rsp+0E8h+arg_0], rax
0x180038b3c  mov     r14, [rax]
0x180038b3f  movzx   eax, byte ptr [r14+87h]
0x180038b47  movzx   ecx, byte ptr [r14+86h]
0x180038b4f  movzx   edx, byte ptr [r14+85h]
0x180038b57  movzx   r8d, byte ptr [r14+84h]
0x180038b5f  movzx   r9d, byte ptr [r14+83h]
0x180038b67  movzx   r10d, byte ptr [r14+82h]
0x180038b6f  movzx   r11d, byte ptr [r14+81h]
0x180038b77  movzx   ebx, byte ptr [r14+80h]
0x180038b7f  movzx   edi, word ptr [r14+7Eh]
0x180038b84  movzx   esi, word ptr [r14+7Ch]
0x180038b89  mov     [rsp+0E8h+var_70], eax
0x180038b8d  mov     [rsp+0E8h+var_78], ecx
0x180038b91  mov     [rsp+0E8h+var_80], edx
0x180038b95  mov     [rsp+0E8h+var_88], r8d
0x180038b9a  mov     [rsp+0E8h+var_90], r9d
0x180038b9f  mov     dword ptr [rsp+0E8h+var_98], r10d
0x180038ba4  mov     dword ptr [rsp+0E8h+var_A0], r11d
0x180038ba9  mov     dword ptr [rsp+0E8h+var_A8], ebx
0x180038bad  mov     dword ptr [rsp+0E8h+MessageGuid], edi
0x180038bb1  mov     dword ptr [rsp+0E8h+var_B8], esi
0x180038bb5  mov     eax, [r14+78h]
0x180038bb9  mov     dword ptr [rsp+0E8h+var_C0], eax
0x180038bbd  mov     [rsp+0E8h+var_C8], 8Ah; unsigned int
0x180038bc5  lea     r9, aOnecoreuapTerm_10; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180038bcc  lea     r8, aRdpAvencSinkwr_8; "Rdp::Avenc::SinkWriter::CSinkWriterFram"...
0x180038bd3  lea     rdx, aSinkwriterfram; "SinkWriterFrameProcessorStop: Id {%08lX"...
0x180038bda  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x180038be1  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x180038be6  mov     rcx, [r13+30h]; this
0x180038bea  test    rcx, rcx
0x180038bed  jz      short loc_180038C10
0x180038bef  call    ?Stop@CMFEncoder@SinkWriter@Avenc@Rdp@@QEAAXXZ; Rdp::Avenc::SinkWriter::CMFEncoder::Stop(void)
0x180038bf4  mov     rcx, [r13+30h]
0x180038bf8  mov     [r13+30h], r15
0x180038bfc  test    rcx, rcx
0x180038bff  jz      short loc_180038C10
0x180038c01  mov     rax, [rcx]
0x180038c04  mov     edx, r12d
0x180038c07  mov     rax, [rax+18h]
0x180038c0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038c10  lea     rdi, [r13+28h]
0x180038c14  mov     rcx, rdi; Address
0x180038c17  call    ?_Lock_and_load@?$_Locked_pointer@V_Ref_count_base@std@@@std@@QEAAPEAV_Ref_count_base@2@XZ; std::_Locked_pointer<std::_Ref_count_base>::_Lock_and_load(void)
0x180038c1c  mov     rbx, rax
0x180038c1f  mov     [rsp+0E8h+arg_8], rax
0x180038c27  mov     rsi, [r13+20h]
0x180038c2b  mov     [rsp+0E8h+var_50], rsi
0x180038c33  mov     [rsp+0E8h+var_48], rax
0x180038c3b  test    rax, rax
0x180038c3e  jz      short loc_180038C45
0x180038c40  lock add [rax+8], r12d
0x180038c45  mov     rdx, rax
0x180038c48  xchg    rdx, [rdi]
0x180038c4b  and     dl, 3
0x180038c4e  cmp     dl, 2
0x180038c51  jnz     short loc_180038C5D
0x180038c53  mov     rcx, rdi; Address
0x180038c56  call    cs:__imp_WakeByAddressAll
0x180038c5c  nop
0x180038c5d  xorps   xmm0, xmm0
0x180038c60  movdqu  [rsp+0E8h+var_60], xmm0
0x180038c69  lea     rdx, [rsp+0E8h+var_60]
0x180038c71  lea     rcx, [r13+20h]
0x180038c75  call    ?store@?$atomic@V?$shared_ptr@V?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@@std@@@std@@QEAAXV?$shared_ptr@V?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@@2@W4memory_order@2@@Z; std::atomic<std::shared_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>>>::store(std::shared_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>>,std::memory_order)
0x180038c7a  test    rsi, rsi
0x180038c7d  jz      loc_180038D13
0x180038c83  xor     r9d, r9d; unsigned __int64
0x180038c86  xor     r8d, r8d; unsigned int
0x180038c89  mov     edx, 1000h; unsigned __int64
0x180038c8e  mov     rcx, rsi; this
0x180038c91  call    ?AllocatePool@CFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@QEAAX_KI0@Z; Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::AllocatePool(unsigned __int64,uint,unsigned __int64)
0x180038c96  mov     r14, [rsp+0E8h+arg_0]
0x180038c9e  mov     rax, [r14]
0x180038ca1  mov     r13d, [rax+88h]
0x180038ca8  mov     edx, 0Ah; unsigned __int64
0x180038cad  mov     rcx, rsi; this
0x180038cb0  call    ?EnsureBuffer@CFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@QEAAPEAX_K@Z; Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::EnsureBuffer(unsigned __int64)
0x180038cb5  mov     rdi, rax
0x180038cb8  mov     rcx, [rsp+0E8h]
0x180038cc0  lea     rax, aUnableToEnsure_20; "Unable to ensure RDPGFX_DELETE_SURFACE_"...
0x180038cc7  mov     [rsp+0E8h+var_C0], rax
0x180038ccc  mov     qword ptr [rsp+0E8h+var_C8], rdi
0x180038cd1  mov     r9d, 8007000Eh
0x180038cd7  lea     r8, aOnecoreuapTerm_14; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x180038cde  mov     edx, 157h
0x180038ce3  call    ??$Throw_HrIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBDJ01ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(void *,uint,char const *,long,void *,char const *,...)
0x180038ce8  mov     eax, 0Ah
0x180038ced  mov     [rdi], eax
0x180038cef  mov     [rdi+4], eax
0x180038cf2  mov     [rdi+8], r13w
0x180038cf7  mov     rcx, rsi; this
0x180038cfa  call    ?Flush@CFcWireEncoder@Avenc@Rdp@@QEAAXI@Z; Rdp::Avenc::CFcWireEncoder::Flush(uint)
0x180038cff  nop
0x180038d00  jmp     short loc_180038D1B
0x180038d02  mov     r12d, 1
0x180038d08  xor     r15d, r15d
0x180038d0b  mov     rbx, [rsp+0E8h+arg_8]
0x180038d13  mov     r14, [rsp+0E8h+arg_0]
0x180038d1b  lea     rdi, WPP_GLOBAL_Control
0x180038d22  lea     rsi, WPP_RECORDER_INITIALIZED
0x180038d29  lea     r13, WPP_dce8caabb58138b44d6f1d43a0cfbbf0_Traceguids
0x180038d30  mov     rcx, [r14]
0x180038d33  mov     [r14], r15
0x180038d36  test    rcx, rcx
0x180038d39  jz      short loc_180038D48
0x180038d3b  mov     rax, [rcx]
0x180038d3e  mov     rax, [rax+10h]
0x180038d42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038d47  nop
0x180038d48  mov     rax, cs:WPP_GLOBAL_Control
0x180038d4f  cmp     rax, rdi
0x180038d52  jz      short loc_180038D60
0x180038d54  test    [rax+1Ch], r12b
0x180038d58  jz      short loc_180038D60
0x180038d5a  cmp     byte ptr [rax+19h], 4
0x180038d5e  jnb     short loc_180038D63
0x180038d60  mov     r12b, r15b
0x180038d63  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x180038d6a  setnz   dil
0x180038d6e  test    r12b, r12b
0x180038d71  jnz     short loc_180038D78
0x180038d73  test    dil, dil
0x180038d76  jz      short loc_180038DA9
0x180038d78  call    cs:__imp_GetCurrentThreadId
0x180038d7e  mov     dword ptr [rsp+0E8h+var_A8], eax; char
0x180038d82  mov     [rsp+0E8h+MessageGuid], r13; MessageGuid
0x180038d87  mov     [rsp+0E8h+var_B8], 0Dh; __int16
0x180038d8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180038d95  mov     r9, [rcx+28h]; int
0x180038d99  mov     r8b, dil; int
0x180038d9c  mov     dl, r12b; int
0x180038d9f  mov     rcx, [rcx+10h]; int
0x180038da3  call    WPP_RECORDER_AND_TRACE_SF_D
0x180038da8  nop
0x180038da9  test    rbx, rbx
0x180038dac  jz      short loc_180038DE4
0x180038dae  or      edi, 0FFFFFFFFh
0x180038db1  mov     eax, edi
0x180038db3  lock xadd [rbx+8], eax
0x180038db8  add     eax, edi
0x180038dba  jnz     short loc_180038DE4
0x180038dbc  mov     rax, [rbx]
0x180038dbf  mov     rcx, rbx
0x180038dc2  mov     rax, [rax]
0x180038dc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038dca  mov     eax, edi
0x180038dcc  lock xadd [rbx+0Ch], eax
0x180038dd1  add     eax, edi
0x180038dd3  jnz     short loc_180038DE4
0x180038dd5  mov     rax, [rbx]
0x180038dd8  mov     rcx, rbx
0x180038ddb  mov     rax, [rax+8]
0x180038ddf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038de4  xor     eax, eax
0x180038de6  jmp     short loc_180038DEF
0x180038de8  mov     eax, dword ptr [rsp+0E8h+arg_0]
0x180038def  add     rsp, 0B0h
0x180038df6  pop     r15
0x180038df8  pop     r14
0x180038dfa  pop     r13
0x180038dfc  pop     r12
0x180038dfe  pop     rdi
0x180038dff  pop     rsi
0x180038e00  pop     rbx
0x180038e01  retn
```
