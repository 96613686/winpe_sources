# Rdp::Avenc::RdpProg::CRdpProgFrameProcessor::Start(void)

- ea: `0x180067c50`
- end: `0x18006834c`
- name: `?Start@CRdpProgFrameProcessor@RdpProg@Avenc@Rdp@@UEAAJXZ`
- size: `1788`
- prototype: `__int64 __fastcall(Rdp::Avenc::RdpProg::CRdpProgFrameProcessor *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180065f40`

## callees

- `0x180002b38`
- `0x180003604`
- `0x1800065a4`
- `0x18000e848`
- `0x18000ec04`
- `0x18001143c`
- `0x180011490`
- `0x1800152c4`
- `0x180015480`
- `0x180022fb8`
- `0x180023b34`
- `0x180023ee4`
- `0x180028840`
- `0x18002aa1c`
- `0x18002aac0`
- `0x18002b904`
- `0x18002dd40`
- `0x18002e0c4`
- `0x180067c50`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180067cad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800682a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180067cad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800682a8`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18006814e`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18006814e`

## string_xrefs

- `0x180068339`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x1800681c5`: `onecoreuap\termsrv\rdp_bin\win\common/protocol/RdpEgfx/RdpEgfx.h`
- `0x1800681ae`: `Unable to ensure RDPGFX_CREATE_SURFACE_PDU_SIZE`
- `0x180067f02`: `Failed to create frame encoder`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Rdp::Avenc::RdpProg::CRdpProgFrameProcessor::Start(
        Rdp::Avenc::RdpProg::CRdpProgFrameProcessor *this,
        __int64 a2,
        int a3,
        int a4)
{
  char v5; // r14
  char v6; // bl
  bool v7; // di
  char CurrentThreadId; // al
  int v9; // r8d
  int v10; // edx
  __int64 v11; // rdx
  const struct _tlgProvider_t *v12; // rax
  int v13; // r8d
  int v14; // r9d
  _QWORD *v15; // rax
  void (__fastcall ***v16)(_QWORD, __int64); // rcx
  unsigned int v17; // eax
  __int64 v18; // rax
  __int64 v19; // r15
  unsigned int v20; // r12d
  unsigned int v21; // r13d
  char *v22; // rdi
  volatile signed __int32 *v23; // rbx
  int v24; // eax
  __int64 v25; // rbx
  volatile signed __int32 *v26; // rbx
  __int64 v27; // rax
  const char *v28; // r9
  volatile signed __int32 *v29; // rbx
  Rdp::Avenc::CFcWireEncoderWithBulkUncompressed *v30; // r15
  _DWORD *v31; // rax
  int v32; // r13d
  _DWORD *v33; // r12
  __int64 v34; // r8
  int v35; // edx
  unsigned int v36; // edx
  bool v37; // si
  char v38; // al
  int v39; // r8d
  int v40; // edx
  __int64 result; // rax
  int v42; // [rsp+20h] [rbp-A8h]
  int v43; // [rsp+20h] [rbp-A8h]
  int v44; // [rsp+28h] [rbp-A0h]
  int v45; // [rsp+28h] [rbp-A0h]
  int *v46; // [rsp+60h] [rbp-68h] BYREF
  const char *v47; // [rsp+68h] [rbp-60h] BYREF
  _QWORD v48[2]; // [rsp+70h] [rbp-58h] BYREF
  const char *v49; // [rsp+80h] [rbp-48h] BYREF
  __int64 v50; // [rsp+88h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]
  char *v52; // [rsp+D8h] [rbp+10h] BYREF
  const char *v53; // [rsp+E0h] [rbp+18h] BYREF
  const char *v54; // [rsp+E8h] [rbp+20h] BYREF

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
      v42,
      v44,
      10,
      &WPP_a6c7f7db86c33c0e0753adfc7a80bf79_Traceguids,
      CurrentThreadId);
  }
  if ( (unsigned int)dword_1800C1058 > 4
    && (qword_1800C1068 & 0x470000000000LL) != 0
    && (qword_1800C1070 & 0x470000000000LL) == qword_1800C1070 )
  {
    v11 = *((_QWORD *)this + 6);
    LODWORD(v52) = *(_DWORD *)(*(_QWORD *)(v11 + 112) + 160LL);
    v53 = (const char *)(v11 + 120);
    v54 = "Start RdpProg frame processor";
    v46 = &xmmword_1800C21A0;
    v47 = "RdpAvenc";
    v48[0] = 0x1000000;
    v49 = "Checkpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_1800C1058,
      (unsigned int)&byte_1800B55C7,
      a3,
      a4,
      (__int64)&v49,
      (__int64)v48,
      (__int64)&v47,
      (__int64)&v46,
      (__int64)&v54,
      (__int64)&v53,
      (__int64)&v52);
  }
  try
  {
    Rdp::Modern::Utils::CInflightRecorder::push0(
      (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      L"RdpProgFrameProcessorStart",
      "Rdp::Avenc::RdpProg::CRdpProgFrameProcessor::Start",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rdpprogprocessor\\rdpprogframeprocessor.cpp",
      0x3Fu);
    v12 = RdpGrfxPipelinePerfProvider::Provider();
    if ( *(_DWORD *)v12 > 5u )
    {
      v52 = (char *)this - 80;
      v53 = "Start";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        (_DWORD)v12,
        (unsigned int)word_1800B559A,
        v13,
        v14,
        (__int64)&v53,
        (__int64)&v52);
    }
    v53 = (const char *)(*(_QWORD *)(*((_QWORD *)this + 6) + 112LL) + 288LL);
    wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(
      retaddr,
      71,
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rdpprogprocessor\\rdpprogframeprocessor.cpp",
      2147500035LL);
    if ( *((_DWORD *)this + 60) )
    {
      v15 = 0;
    }
    else
    {
      v15 = operator new(0x20u);
      *v15 = &Rdp::Avenc::RdpProg::CProgressiveEncoder::`vftable';
      v15[1] = 0;
      *((_DWORD *)v15 + 4) = 0;
      v15[3] = 0;
    }
    v16 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 29);
    *((_QWORD *)this + 29) = v15;
    if ( v16 )
      (**v16)(v16, 1);
    wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(
      retaddr,
      77,
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rdpprogprocessor\\rdpprogframeprocessor.cpp",
      2147942414LL);
    v17 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 29) + 8LL))(
            *((_QWORD *)this + 29),
            *(unsigned int *)(*((_QWORD *)this + 6) + 148LL),
            *(unsigned int *)(*((_QWORD *)this + 6) + 152LL));
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x53,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rdpprogprocessor\\rdpprogframeprocessor.cpp",
      (const char *)v17,
      (int)"Frame encoder initialization failed",
      "Failed to create frame encoder");
    v18 = *((_QWORD *)this + 6);
    v19 = v18 + 176;
    v20 = *(_DWORD *)(v18 + 152);
    v21 = *(_DWORD *)(v18 + 148);
    v22 = (char *)operator new(0xD0u);
    v52 = v22;
    *((_DWORD *)v22 + 2) = 1;
    *((_DWORD *)v22 + 3) = 1;
    *(_QWORD *)v22 = &std::_Ref_count_obj2<Rdp::Avenc::CBitRateController<Rdp::Avenc::H265_420_Profile>>::`vftable';
    Rdp::Avenc::CBitRateController<Rdp::Avenc::H265_420_Profile>::CBitRateController<Rdp::Avenc::H265_420_Profile>(
      v22 + 16,
      v21,
      v20,
      v19);
    *((_QWORD *)this + 7) = v22 + 16;
    v23 = (volatile signed __int32 *)*((_QWORD *)this + 8);
    *((_QWORD *)this + 8) = v22;
    if ( v23 )
    {
      if ( _InterlockedExchangeAdd(v23 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
        if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
      }
    }
    v52 = 0;
    v24 = (**((__int64 (__fastcall ***)(char *, GUID *, char **))this - 10))(
            (char *)this - 80,
            &GUID_a06bc936_6fd4_47ff_9fc7_68fe54155cab,
            &v52);
    if ( v24 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v24,
        v43);
    v54 = v52;
    v53 = *(const char **)v53;
    v25 = std::make_shared<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>,Rdp::Avenc::IFileIoChannel1 *,Rdp::Avenc::IIoPacketCompleteEvents *>(
            v48,
            &v53,
            &v54);
    v49 = *(const char **)v25;
    v50 = *(_QWORD *)(v25 + 8);
    *(_QWORD *)v25 = 0;
    *(_QWORD *)(v25 + 8) = 0;
    std::atomic<std::shared_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>>>::store(
      (char *)this + 32,
      &v49);
    v26 = *(volatile signed __int32 **)(v25 + 8);
    if ( v26 )
    {
      if ( _InterlockedExchangeAdd(v26 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
        if ( _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
      }
    }
    if ( v52 )
      (*(void (__fastcall **)(char *))(*(_QWORD *)v52 + 16LL))(v52);
    v27 = std::_Locked_pointer<std::_Ref_count_base>::_Lock_and_load((char *)this + 40);
    v29 = (volatile signed __int32 *)v27;
    v30 = (Rdp::Avenc::CFcWireEncoderWithBulkUncompressed *)*((_QWORD *)this + 4);
    v49 = (const char *)v30;
    v50 = v27;
    if ( v27 )
      _InterlockedAdd((volatile signed __int32 *)(v27 + 8), 1u);
    if ( (_InterlockedExchange64((volatile __int64 *)this + 5, v27) & 3) == 2 )
      WakeByAddressAll((char *)this + 40);
    if ( v30 )
    {
      Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::AllocatePool(v30, 0x1000u, 0, 0);
      v31 = (_DWORD *)*((_QWORD *)this + 6);
      v32 = v31[38];
      LODWORD(v53) = v31[37];
      LODWORD(v52) = v31[34];
      v33 = Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::EnsureBuffer(v30, 0xFu);
      wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(
        retaddr,
        266,
        "onecoreuap\\termsrv\\rdp_bin\\win\\common/protocol/RdpEgfx/RdpEgfx.h",
        2147942414LL,
        v33,
        "Unable to ensure RDPGFX_CREATE_SURFACE_PDU_SIZE");
      *v33 = 9;
      v33[1] = 15;
      *((_WORD *)v33 + 4) = (_WORD)v52;
      *((_WORD *)v33 + 5) = (_WORD)v53;
      *((_WORD *)v33 + 6) = v32;
      *((_BYTE *)v33 + 14) = 32;
      v34 = *((_QWORD *)this + 6);
      Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>::MapSurfaceToScaledOutput(
        (_DWORD)v30,
        v35,
        *(_DWORD *)(v34 + 136),
        *(_DWORD *)(*(_QWORD *)(v34 + 112) + 164LL),
        *(_DWORD *)(*(_QWORD *)(v34 + 112) + 168LL),
        *(_DWORD *)(v34 + 140),
        *(_DWORD *)(v34 + 144),
        *(_DWORD *)(v34 + 148),
        *(_DWORD *)(v34 + 152));
      Rdp::Avenc::CFcWireEncoder::Flush(v30, v36);
    }
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v5 = 0;
    }
    v37 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v38 = GetCurrentThreadId();
      LOBYTE(v39) = v37;
      LOBYTE(v40) = v5;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v40,
        v39,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v43,
        v45,
        11,
        &WPP_a6c7f7db86c33c0e0753adfc7a80bf79_Traceguids,
        v38);
    }
    if ( v29 )
    {
      if ( _InterlockedExchangeAdd(v29 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v29)(v29);
        if ( _InterlockedExchangeAdd(v29 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 8LL))(v29);
      }
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x83,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rdpprogprocessor\\rdpprogframeprocessor.cpp",
                           v28);
  }
  return result;
}

```

## disassembly

```asm
0x180067c50  push    rbx
0x180067c52  push    rsi
0x180067c53  push    rdi
0x180067c54  push    r12
0x180067c56  push    r13
0x180067c58  push    r14
0x180067c5a  push    r15
0x180067c5c  sub     rsp, 90h
0x180067c63  mov     rsi, rcx
0x180067c66  xor     r15d, r15d
0x180067c69  lea     rcx, WPP_GLOBAL_Control
0x180067c70  mov     rax, cs:WPP_GLOBAL_Control
0x180067c77  lea     r14d, [r15+1]
0x180067c7b  cmp     rax, rcx
0x180067c7e  jz      short loc_180067C8F
0x180067c80  test    [rax+1Ch], r14b
0x180067c84  jz      short loc_180067C8F
0x180067c86  cmp     byte ptr [rax+19h], 4
0x180067c8a  mov     bl, r14b
0x180067c8d  jnb     short loc_180067C92
0x180067c8f  mov     bl, r15b
0x180067c92  lea     rax, WPP_RECORDER_INITIALIZED
0x180067c99  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180067ca0  setnz   dil
0x180067ca4  test    bl, bl
0x180067ca6  jnz     short loc_180067CAD
0x180067ca8  test    dil, dil
0x180067cab  jz      short loc_180067CE6
0x180067cad  call    cs:__imp_GetCurrentThreadId
0x180067cb3  mov     dword ptr [rsp+0C8h+var_88], eax; char
0x180067cb7  lea     r15, WPP_a6c7f7db86c33c0e0753adfc7a80bf79_Traceguids
0x180067cbe  mov     [rsp+0C8h+MessageGuid], r15; MessageGuid
0x180067cc3  mov     [rsp+0C8h+var_98], 0Ah; __int16
0x180067cca  mov     rcx, cs:WPP_GLOBAL_Control
0x180067cd1  mov     r9, [rcx+28h]; int
0x180067cd5  mov     r8b, dil; int
0x180067cd8  mov     dl, bl; int
0x180067cda  mov     rcx, [rcx+10h]; int
0x180067cde  call    WPP_RECORDER_AND_TRACE_SF_D
0x180067ce3  xor     r15d, r15d
0x180067ce6  mov     eax, cs:dword_1800C1058
0x180067cec  cmp     eax, 4
0x180067cef  jbe     loc_180067DEA
0x180067cf5  mov     rcx, cs:qword_1800C1070
0x180067cfc  mov     rax, cs:qword_1800C1068
0x180067d03  mov     rdx, 470000000000h
0x180067d0d  test    rdx, rax
0x180067d10  jz      loc_180067DEA
0x180067d16  mov     rax, rcx
0x180067d19  and     rax, rdx
0x180067d1c  cmp     rax, rcx
0x180067d1f  jnz     loc_180067DEA
0x180067d25  mov     rdx, [rsi+30h]
0x180067d29  mov     rax, [rdx+70h]
0x180067d2d  mov     ecx, [rax+0A0h]
0x180067d33  mov     dword ptr [rsp+0C8h+arg_8], ecx
0x180067d3a  lea     rax, [rdx+78h]
0x180067d3e  mov     [rsp+0C8h+arg_10], rax
0x180067d46  lea     rax, aStartRdpprogFr; "Start RdpProg frame processor"
0x180067d4d  mov     [rsp+0C8h+arg_18], rax
0x180067d55  lea     rax, xmmword_1800C21A0
0x180067d5c  mov     [rsp+0C8h+var_68], rax
0x180067d61  lea     rax, aRdpavenc; "RdpAvenc"
0x180067d68  mov     [rsp+0C8h+var_60], rax
0x180067d6d  mov     [rsp+0C8h+var_58], 1000000h
0x180067d76  lea     rax, aCheckpoint; "Checkpoint"
0x180067d7d  mov     [rsp+0C8h+var_48], rax
0x180067d85  lea     rax, [rsp+0C8h+arg_8]
0x180067d8d  mov     [rsp+0C8h+var_78], rax
0x180067d92  lea     rax, [rsp+0C8h+arg_10]
0x180067d9a  mov     [rsp+0C8h+var_80], rax
0x180067d9f  lea     rax, [rsp+0C8h+arg_18]
0x180067da7  mov     qword ptr [rsp+0C8h+var_88], rax
0x180067dac  lea     rax, [rsp+0C8h+var_68]
0x180067db1  mov     [rsp+0C8h+MessageGuid], rax
0x180067db6  lea     rax, [rsp+0C8h+var_60]
0x180067dbb  mov     qword ptr [rsp+0C8h+var_98], rax
0x180067dc0  lea     rax, [rsp+0C8h+var_58]
0x180067dc5  mov     [rsp+0C8h+var_A0], rax
0x180067dca  lea     rax, [rsp+0C8h+var_48]
0x180067dd2  mov     qword ptr [rsp+0C8h+var_A8], rax
0x180067dd7  lea     rdx, byte_1800B55C7
0x180067dde  lea     rcx, dword_1800C1058
0x180067de5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U3@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@35AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x180067dea  mov     [rsp+0C8h+var_A8], 3Fh ; '?'; unsigned int
0x180067df2  lea     rdi, aOnecoreuapTerm_35; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180067df9  mov     r9, rdi; char *
0x180067dfc  lea     r8, aRdpAvencRdppro_7; "Rdp::Avenc::RdpProg::CRdpProgFrameProce"...
0x180067e03  lea     rdx, aRdpprogframepr_0; "RdpProgFrameProcessorStart"
0x180067e0a  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x180067e11  call    ?push0@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1I@Z; Rdp::Modern::Utils::CInflightRecorder::push0(ushort const *,char const *,char const *,uint)
0x180067e16  call    ?Provider@RdpGrfxPipelinePerfProvider@@SAPEBU_tlgProvider_t@@XZ; RdpGrfxPipelinePerfProvider::Provider(void)
0x180067e1b  mov     ecx, [rax]
0x180067e1d  cmp     ecx, 5
0x180067e20  jbe     short loc_180067E66
0x180067e22  lea     rcx, [rsi-50h]
0x180067e26  mov     [rsp+0C8h+arg_8], rcx
0x180067e2e  lea     rcx, aStart; "Start"
0x180067e35  mov     [rsp+0C8h+arg_10], rcx
0x180067e3d  lea     rcx, [rsp+0C8h+arg_8]
0x180067e45  mov     [rsp+0C8h+var_A0], rcx
0x180067e4a  lea     rcx, [rsp+0C8h+arg_10]
0x180067e52  mov     qword ptr [rsp+0C8h+var_A8], rcx
0x180067e57  lea     rdx, word_1800B559A
0x180067e5e  mov     rcx, rax
0x180067e61  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180067e66  mov     rax, [rsi+30h]
0x180067e6a  mov     rax, [rax+70h]
0x180067e6e  add     rax, 120h
0x180067e74  mov     [rsp+0C8h+arg_10], rax
0x180067e7c  mov     rcx, [rsp+0C8h]
0x180067e84  lea     rdx, aGraphicsFileIO; "Graphics file I/O channel is not availa"...
0x180067e8b  mov     [rsp+0C8h+var_A0], rdx
0x180067e90  mov     qword ptr [rsp+0C8h+var_A8], rax
0x180067e95  mov     r9d, 80004003h
0x180067e9b  mov     r8, rdi
0x180067e9e  mov     edx, 47h ; 'G'
0x180067ea3  call    ??$Throw_HrIfNullMsg@V?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@wil@@$0A@@in1diag3@details@wil@@YAXPEAXIPEBDJAEBV?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@2@1ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(void *,uint,char const *,long,wil::com_ptr_t<IPropertyStore,wil::err_exception_policy> const &,char const *,...)
0x180067ea8  cmp     [rsi+0F0h], r15d
0x180067eaf  jz      short loc_180067EB6
0x180067eb1  mov     rax, r15
0x180067eb4  jmp     short loc_180067EDA
0x180067eb6  mov     ecx, 20h ; ' '; Size
0x180067ebb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180067ec0  lea     rcx, ??_7CProgressiveEncoder@RdpProg@Avenc@Rdp@@6B@; const Rdp::Avenc::RdpProg::CProgressiveEncoder::`vftable'
0x180067ec7  mov     [rax], rcx
0x180067eca  mov     qword ptr [rax+8], 0
0x180067ed2  mov     [rax+10h], r15d
0x180067ed6  mov     [rax+18h], r15
0x180067eda  lea     rbx, [rsi+0E8h]
0x180067ee1  mov     rcx, [rbx]
0x180067ee4  mov     [rbx], rax
0x180067ee7  test    rcx, rcx
0x180067eea  jz      short loc_180067EFA
0x180067eec  mov     rax, [rcx]
0x180067eef  mov     edx, r14d
0x180067ef2  mov     rax, [rax]
0x180067ef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067efa  mov     rcx, [rsp+0C8h]
0x180067f02  lea     rax, aFailedToCreate_12; "Failed to create frame encoder"
0x180067f09  mov     [rsp+0C8h+var_A0], rax; char *
0x180067f0e  mov     qword ptr [rsp+0C8h+var_A8], rbx
0x180067f13  mov     r9d, 8007000Eh
0x180067f19  mov     r8, rdi
0x180067f1c  mov     edx, 4Dh ; 'M'
0x180067f21  call    ??$Throw_HrIfNullMsg@V?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@wil@@$0A@@in1diag3@details@wil@@YAXPEAXIPEBDJAEBV?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@2@1ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(void *,uint,char const *,long,wil::com_ptr_t<IPropertyStore,wil::err_exception_policy> const &,char const *,...)
0x180067f26  mov     rcx, [rbx]
0x180067f29  mov     rdx, [rsi+30h]
0x180067f2d  mov     rax, [rcx]
0x180067f30  mov     r8d, [rdx+98h]
0x180067f37  mov     edx, [rdx+94h]
0x180067f3d  mov     rax, [rax+8]
0x180067f41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067f46  mov     rcx, [rsp+0C8h]; this
0x180067f4e  lea     rdx, aFrameEncoderIn; "Frame encoder initialization failed"
0x180067f55  mov     qword ptr [rsp+0C8h+var_A8], rdx; int
0x180067f5a  mov     r9d, eax; char *
0x180067f5d  mov     r8, rdi; unsigned int
0x180067f60  mov     edx, 53h ; 'S'; void *
0x180067f65  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180067f6a  mov     rax, [rsi+30h]
0x180067f6e  lea     r15, [rax+0B0h]
0x180067f75  mov     r12d, [rax+98h]
0x180067f7c  mov     r13d, [rax+94h]
0x180067f83  mov     ecx, 0D0h; Size
0x180067f88  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180067f8d  mov     rdi, rax
0x180067f90  mov     [rsp+0C8h+arg_8], rax
0x180067f98  mov     [rax+8], r14d
0x180067f9c  mov     [rax+0Ch], r14d
0x180067fa0  lea     rax, ??_7?$_Ref_count_obj2@V?$CBitRateController@UH265_420_Profile@Avenc@Rdp@@@Avenc@Rdp@@@std@@6B@; const std::_Ref_count_obj2<Rdp::Avenc::CBitRateController<Rdp::Avenc::H265_420_Profile>>::`vftable'
0x180067fa7  mov     [rdi], rax
0x180067faa  lea     rbx, [rdi+10h]
0x180067fae  mov     r9, r15
0x180067fb1  mov     r8d, r12d
0x180067fb4  mov     edx, r13d
0x180067fb7  mov     rcx, rbx
0x180067fba  call    ??0?$CBitRateController@UH265_420_Profile@Avenc@Rdp@@@Avenc@Rdp@@QEAA@IIAEBUDXGI_RATIONAL@@@Z; Rdp::Avenc::CBitRateController<Rdp::Avenc::H265_420_Profile>::CBitRateController<Rdp::Avenc::H265_420_Profile>(uint,uint,DXGI_RATIONAL const &)
0x180067fbf  nop
0x180067fc0  mov     [rsi+38h], rbx
0x180067fc4  mov     rbx, [rsi+40h]
0x180067fc8  mov     [rsi+40h], rdi
0x180067fcc  or      edi, 0FFFFFFFFh
0x180067fcf  test    rbx, rbx
0x180067fd2  jz      short loc_180068007
0x180067fd4  mov     eax, edi
0x180067fd6  lock xadd [rbx+8], eax
0x180067fdb  add     eax, edi
0x180067fdd  jnz     short loc_180068007
0x180067fdf  mov     rax, [rbx]
0x180067fe2  mov     rcx, rbx
0x180067fe5  mov     rax, [rax]
0x180067fe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067fed  mov     eax, edi
0x180067fef  lock xadd [rbx+0Ch], eax
0x180067ff4  add     eax, edi
0x180067ff6  jnz     short loc_180068007
0x180067ff8  mov     rax, [rbx]
0x180067ffb  mov     rcx, rbx
0x180067ffe  mov     rax, [rax+8]
0x180068002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068007  lea     rcx, [rsi-50h]
0x18006800b  mov     [rsp+0C8h+arg_8], 0
0x180068017  mov     rax, [rcx]
0x18006801a  lea     r8, [rsp+0C8h+arg_8]
0x180068022  lea     rdx, _GUID_a06bc936_6fd4_47ff_9fc7_68fe54155cab
0x180068029  mov     rax, [rax]
0x18006802c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068031  mov     rcx, [rsp+0C8h]; this
0x180068039  test    eax, eax
0x18006803b  js      loc_180068336
0x180068041  mov     rax, [rsp+0C8h+arg_8]
0x180068049  mov     [rsp+0C8h+arg_18], rax
0x180068051  mov     rax, [rsp+0C8h+arg_10]
0x180068059  mov     rax, [rax]
0x18006805c  mov     [rsp+0C8h+arg_10], rax
0x180068064  lea     r8, [rsp+0C8h+arg_18]
0x18006806c  lea     rdx, [rsp+0C8h+arg_10]
0x180068074  lea     rcx, [rsp+0C8h+var_58]
0x180068079  call    ??$make_shared@V?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@PEAUIFileIoChannel1@Avenc@3@PEAUIIoPacketCompleteEvents@53@@std@@YA?AV?$shared_ptr@V?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@@0@$$QEAPEAUIFileIoChannel1@Avenc@Rdp@@$$QEAPEAUIIoPacketCompleteEvents@34@@Z; std::make_shared<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>,Rdp::Avenc::IFileIoChannel1 *,Rdp::Avenc::IIoPacketCompleteEvents *>(Rdp::Avenc::IFileIoChannel1 * &&,Rdp::Avenc::IIoPacketCompleteEvents * &&)
0x18006807e  mov     rbx, rax
0x180068081  mov     rcx, [rax]
0x180068084  mov     [rsp+0C8h+var_48], rcx
0x18006808c  mov     rcx, [rax+8]
0x180068090  mov     [rsp+0C8h+var_40], rcx
0x180068098  mov     qword ptr [rax], 0
0x18006809f  mov     qword ptr [rax+8], 0
0x1800680a7  lea     rcx, [rsi+20h]
0x1800680ab  lea     rdx, [rsp+0C8h+var_48]
0x1800680b3  call    ?store@?$atomic@V?$shared_ptr@V?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@@std@@@std@@QEAAXV?$shared_ptr@V?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@@2@W4memory_order@2@@Z; std::atomic<std::shared_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>>>::store(std::shared_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>>,std::memory_order)
0x1800680b8  mov     rbx, [rbx+8]
0x1800680bc  test    rbx, rbx
0x1800680bf  jz      short loc_1800680F5
0x1800680c1  mov     eax, edi
0x1800680c3  lock xadd [rbx+8], eax
0x1800680c8  add     eax, edi
0x1800680ca  jnz     short loc_1800680F5
0x1800680cc  mov     rax, [rbx]
0x1800680cf  mov     rcx, rbx
0x1800680d2  mov     rax, [rax]
0x1800680d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800680da  mov     eax, edi
0x1800680dc  lock xadd [rbx+0Ch], eax
0x1800680e1  add     eax, edi
0x1800680e3  jnz     short loc_1800680F5
0x1800680e5  mov     rax, [rbx]
0x1800680e8  mov     rcx, rbx
0x1800680eb  mov     rax, [rax+8]
0x1800680ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800680f4  nop
0x1800680f5  mov     rcx, [rsp+0C8h+arg_8]
0x1800680fd  test    rcx, rcx
0x180068100  jz      short loc_18006810F
0x180068102  mov     rax, [rcx]
0x180068105  mov     rax, [rax+10h]
0x180068109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006810e  nop
0x18006810f  lea     r12, [rsi+28h]
0x180068113  mov     rcx, r12; Address
0x180068116  call    ?_Lock_and_load@?$_Locked_pointer@V_Ref_count_base@std@@@std@@QEAAPEAV_Ref_count_base@2@XZ; std::_Locked_pointer<std::_Ref_count_base>::_Lock_and_load(void)
0x18006811b  mov     rbx, rax
0x18006811e  mov     r15, [rsi+20h]
0x180068122  mov     [rsp+0C8h+var_48], r15
0x18006812a  mov     [rsp+0C8h+var_40], rax
0x180068132  test    rax, rax
0x180068135  jz      short loc_18006813C
0x180068137  lock add [rax+8], r14d
0x18006813c  mov     rdx, rbx
0x18006813f  xchg    rdx, [r12]
0x180068143  and     dl, 3
0x180068146  cmp     dl, 2
0x180068149  jnz     short loc_180068155
0x18006814b  mov     rcx, r12; Address
0x18006814e  call    cs:__imp_WakeByAddressAll
0x180068154  nop
0x180068155  test    r15, r15
0x180068158  jz      loc_18006826A
0x18006815e  xor     r9d, r9d; unsigned __int64
0x180068161  xor     r8d, r8d; unsigned int
0x180068164  mov     edx, 1000h; unsigned __int64
0x180068169  mov     rcx, r15; this
0x18006816c  call    ?AllocatePool@CFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@QEAAX_KI0@Z; Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::AllocatePool(unsigned __int64,uint,unsigned __int64)
0x180068171  mov     rax, [rsi+30h]
0x180068175  mov     r13d, [rax+98h]
0x18006817c  mov     ecx, [rax+94h]
0x180068182  mov     dword ptr [rsp+0C8h+arg_10], ecx
0x180068189  mov     eax, [rax+88h]
0x18006818f  mov     dword ptr [rsp+0C8h+arg_8], eax
0x180068196  mov     edx, 0Fh; unsigned __int64
0x18006819b  mov     rcx, r15; this
0x18006819e  call    ?EnsureBuffer@CFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@QEAAPEAX_K@Z; Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::EnsureBuffer(unsigned __int64)
0x1800681a3  mov     r12, rax
0x1800681a6  mov     rcx, [rsp+0C8h]
0x1800681ae  lea     rax, aUnableToEnsure_2; "Unable to ensure RDPGFX_CREATE_SURFACE_"...
0x1800681b5  mov     [rsp+0C8h+var_A0], rax
0x1800681ba  mov     qword ptr [rsp+0C8h+var_A8], r12
0x1800681bf  mov     r9d, 8007000Eh
0x1800681c5  lea     r8, aOnecoreuapTerm_14; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x1800681cc  mov     edx, 10Ah
0x1800681d1  call    ??$Throw_HrIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBDJ01ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(void *,uint,char const *,long,void *,char const *,...)
  ... truncated ...
```
