# Rdp::Avenc::Raw::CRawFrameProcessor<Rdp::Avenc::ICpuFrameProcessor>::Start(void)

- ea: `0x18003df00`
- end: `0x18003e2a9`
- name: `?Start@?$CRawFrameProcessor@UICpuFrameProcessor@Avenc@Rdp@@@Raw@Avenc@Rdp@@UEAAJXZ`
- size: `937`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180003604`
- `0x1800065a4`
- `0x18000d3a4`
- `0x18001143c`
- `0x1800152c4`
- `0x180015480`
- `0x180038e20`
- `0x180038eb4`
- `0x18003968c`
- `0x180039ff0`
- `0x18003de48`
- `0x18003df00`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003df63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003e25b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003df63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003e25b`

## string_xrefs

- `0x18003e19c`: `onecoreuap\termsrv\rdp_bin\win\common/protocol/RdpEgfx/RdpEgfx.h`
- `0x18003e185`: `Unable to ensure RDPGFX_CREATE_SURFACE_PDU_SIZE`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Rdp::Avenc::Raw::CRawFrameProcessor<Rdp::Avenc::ICpuFrameProcessor>::Start(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4)
{
  char v5; // bl
  bool v6; // di
  bool v7; // si
  char CurrentThreadId; // al
  int v9; // r8d
  int v10; // edx
  __int64 v11; // rdx
  const char *v12; // r9
  struct Rdp::Avenc::IFileIoChannel *v13; // rsi
  Rdp::Avenc::CFcWireEncoderWithBulkCompressor *v14; // rdi
  struct Rdp::Avenc::IIoPacketCompleteEvents *v15; // r8
  Rdp::Avenc::CFcWireEncoderWithBulkCompressor **v16; // rdi
  _QWORD *v17; // rcx
  _DWORD *v18; // rax
  int v19; // r12d
  int v20; // r13d
  __int64 v21; // rsi
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // r9
  int v25; // r8d
  bool v26; // r8
  bool v27; // di
  char v28; // al
  int v29; // r8d
  int v30; // edx
  __int64 result; // rax
  int v32; // [rsp+20h] [rbp-98h]
  int v33; // [rsp+20h] [rbp-98h]
  int v34; // [rsp+28h] [rbp-90h]
  int v35; // [rsp+28h] [rbp-90h]
  int v36; // [rsp+30h] [rbp-88h]
  int *v37; // [rsp+60h] [rbp-58h] BYREF
  const char *v38; // [rsp+68h] [rbp-50h] BYREF
  __int64 v39; // [rsp+70h] [rbp-48h] BYREF
  const char *v40; // [rsp+78h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  Rdp::Avenc::CFcWireEncoderWithBulkCompressor *v42; // [rsp+C8h] [rbp+10h] BYREF
  __int64 v43; // [rsp+D0h] [rbp+18h] BYREF
  const char *v44; // [rsp+D8h] [rbp+20h] BYREF

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
      v32,
      v34,
      10,
      &WPP_4305ebc2891e3311ffa3fc8a7ac47271_Traceguids,
      CurrentThreadId);
  }
  if ( (unsigned int)dword_1800C1058 > 4
    && (qword_1800C1068 & 0x470000000000LL) != 0
    && (qword_1800C1070 & 0x470000000000LL) == qword_1800C1070 )
  {
    v11 = *(_QWORD *)(a1 + 8);
    LODWORD(v42) = *(_DWORD *)(*(_QWORD *)(v11 + 112) + 160LL);
    v43 = v11 + 120;
    v44 = "Start Raw frame processor";
    v37 = &xmmword_1800C21A0;
    v38 = "RdpAvenc";
    v39 = 0x1000000;
    v40 = "Checkpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_1800C1058,
      (unsigned int)&dword_1800AF9B4,
      a3,
      a4,
      (__int64)&v40,
      (__int64)&v39,
      (__int64)&v38,
      (__int64)&v37,
      (__int64)&v44,
      (__int64)&v43,
      (__int64)&v42);
  }
  try
  {
    Rdp::Modern::Utils::CInflightRecorder::push0(
      (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      L"RawFrameProcessorStart",
      "Rdp::Avenc::Raw::CRawFrameProcessor<struct Rdp::Avenc::ICpuFrameProcessor>::Start",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rawprocessor\\rawframeprocessor.cpp",
      0x43u);
    v13 = *(struct Rdp::Avenc::IFileIoChannel **)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 112LL) + 480LL);
    if ( v13 )
    {
      v14 = (Rdp::Avenc::CFcWireEncoderWithBulkCompressor *)operator new(0xC08u);
      v42 = v14;
      Rdp::Avenc::CFcWireEncoderWithBulkCompressor::CFcWireEncoderWithBulkCompressor(v14, v13, v15);
      *((_DWORD *)v14 + 768) = 0;
      v42 = v14;
      v16 = (Rdp::Avenc::CFcWireEncoderWithBulkCompressor **)(a1 + 24);
      std::unique_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>>::operator=<std::default_delete<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>>,0>(
        a1 + 24,
        &v42);
      std::unique_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>>::~unique_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>>(&v42);
      Rdp::Avenc::CFcWireEncoderWithBulkCompressor::AllocatePool(
        *(Rdp::Avenc::CFcWireEncoderWithBulkCompressor **)(a1 + 24),
        0x1000u);
      v17 = *(_QWORD **)(a1 + 24);
      v18 = *(_DWORD **)(a1 + 8);
      v19 = v18[38];
      v20 = v18[37];
      LODWORD(v42) = v18[34];
      v21 = 0;
      v22 = v17[4];
      if ( (unsigned __int64)(v17[5] - v22) >= 0xF )
      {
        v21 = v22 + v17[1];
        v17[4] = v22 + 15;
      }
      wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(
        retaddr,
        266,
        "onecoreuap\\termsrv\\rdp_bin\\win\\common/protocol/RdpEgfx/RdpEgfx.h",
        2147942414LL,
        v21,
        "Unable to ensure RDPGFX_CREATE_SURFACE_PDU_SIZE");
      *(_DWORD *)v21 = 9;
      *(_DWORD *)(v21 + 4) = 15;
      *(_WORD *)(v21 + 8) = (_WORD)v42;
      *(_WORD *)(v21 + 10) = v20;
      *(_WORD *)(v21 + 12) = v19;
      *(_BYTE *)(v21 + 14) = 33;
      v23 = *(_QWORD *)(a1 + 8);
      v24 = *(_QWORD *)(v23 + 112);
      v36 = *(_DWORD *)(v23 + 144);
      v35 = *(_DWORD *)(v23 + 140);
      v25 = *(_DWORD *)(v23 + 136);
      LOBYTE(v23) = *(_BYTE *)(v23 + 200);
      Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>::MapSurfaceToOutput(
        (unsigned int)*v16,
        v23,
        v25,
        *(_DWORD *)(v24 + 164),
        *(_DWORD *)(v24 + 168),
        v35,
        v36);
      Rdp::Avenc::CFcWireEncoderWithBulkCompressor::Flush(*v16, 0, v26);
    }
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v5 = 0;
    }
    v27 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v28 = GetCurrentThreadId();
      LOBYTE(v29) = v27;
      LOBYTE(v30) = v5;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v30,
        v29,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v33,
        v34,
        11,
        &WPP_4305ebc2891e3311ffa3fc8a7ac47271_Traceguids,
        v28);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x67,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rawprocessor\\rawframeprocessor.cpp",
                           v12);
  }
  return result;
}

```

## disassembly

```asm
0x18003df00  push    rbx
0x18003df02  push    rsi
0x18003df03  push    rdi
0x18003df04  push    r12
0x18003df06  push    r13
0x18003df08  push    r14
0x18003df0a  push    r15
0x18003df0c  sub     rsp, 80h
0x18003df13  mov     r14, rcx
0x18003df16  lea     rcx, WPP_GLOBAL_Control
0x18003df1d  mov     rax, cs:WPP_GLOBAL_Control
0x18003df24  mov     bl, 1
0x18003df26  cmp     rax, rcx
0x18003df29  jz      short loc_18003DF3B
0x18003df2b  test    [rax+1Ch], bl
0x18003df2e  jz      short loc_18003DF3B
0x18003df30  cmp     byte ptr [rax+19h], 4
0x18003df34  jb      short loc_18003DF3B
0x18003df36  mov     dil, bl
0x18003df39  jmp     short loc_18003DF3E
0x18003df3b  xor     dil, dil
0x18003df3e  lea     r12, WPP_RECORDER_INITIALIZED
0x18003df45  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18003df4c  setnz   sil
0x18003df50  test    dil, dil
0x18003df53  jnz     short loc_18003DF63
0x18003df55  test    sil, sil
0x18003df58  jnz     short loc_18003DF63
0x18003df5a  lea     r15, WPP_4305ebc2891e3311ffa3fc8a7ac47271_Traceguids
0x18003df61  jmp     short loc_18003DF9A
0x18003df63  call    cs:__imp_GetCurrentThreadId
0x18003df69  mov     dword ptr [rsp+0B8h+var_78], eax; char
0x18003df6d  lea     r15, WPP_4305ebc2891e3311ffa3fc8a7ac47271_Traceguids
0x18003df74  mov     [rsp+0B8h+MessageGuid], r15; MessageGuid
0x18003df79  mov     [rsp+0B8h+var_88], 0Ah; __int16
0x18003df80  mov     rcx, cs:WPP_GLOBAL_Control
0x18003df87  mov     r9, [rcx+28h]; int
0x18003df8b  mov     r8b, sil; int
0x18003df8e  mov     dl, dil; int
0x18003df91  mov     rcx, [rcx+10h]; int
0x18003df95  call    WPP_RECORDER_AND_TRACE_SF_D
0x18003df9a  mov     eax, cs:dword_1800C1058
0x18003dfa0  cmp     eax, 4
0x18003dfa3  jbe     loc_18003E098
0x18003dfa9  mov     rcx, cs:qword_1800C1070
0x18003dfb0  mov     rax, cs:qword_1800C1068
0x18003dfb7  mov     rdx, 470000000000h
0x18003dfc1  test    rdx, rax
0x18003dfc4  jz      loc_18003E098
0x18003dfca  mov     rax, rcx
0x18003dfcd  and     rax, rdx
0x18003dfd0  cmp     rax, rcx
0x18003dfd3  jnz     loc_18003E098
0x18003dfd9  mov     rdx, [r14+8]
0x18003dfdd  mov     rax, [rdx+70h]
0x18003dfe1  mov     ecx, [rax+0A0h]
0x18003dfe7  mov     dword ptr [rsp+0B8h+arg_8], ecx
0x18003dfee  lea     rax, [rdx+78h]
0x18003dff2  mov     [rsp+0B8h+arg_10], rax
0x18003dffa  lea     rax, aStartRawFrameP; "Start Raw frame processor"
0x18003e001  mov     [rsp+0B8h+arg_18], rax
0x18003e009  lea     rax, xmmword_1800C21A0
0x18003e010  mov     [rsp+0B8h+var_58], rax
0x18003e015  lea     rax, aRdpavenc; "RdpAvenc"
0x18003e01c  mov     [rsp+0B8h+var_50], rax
0x18003e021  mov     [rsp+0B8h+var_48], 1000000h
0x18003e02a  lea     rax, aCheckpoint; "Checkpoint"
0x18003e031  mov     [rsp+0B8h+var_40], rax
0x18003e036  lea     rax, [rsp+0B8h+arg_8]
0x18003e03e  mov     [rsp+0B8h+var_68], rax
0x18003e043  lea     rax, [rsp+0B8h+arg_10]
0x18003e04b  mov     [rsp+0B8h+var_70], rax
0x18003e050  lea     rax, [rsp+0B8h+arg_18]
0x18003e058  mov     qword ptr [rsp+0B8h+var_78], rax
0x18003e05d  lea     rax, [rsp+0B8h+var_58]
0x18003e062  mov     [rsp+0B8h+MessageGuid], rax
0x18003e067  lea     rax, [rsp+0B8h+var_50]
0x18003e06c  mov     qword ptr [rsp+0B8h+var_88], rax
0x18003e071  lea     rax, [rsp+0B8h+var_48]
0x18003e076  mov     qword ptr [rsp+0B8h+var_90], rax
0x18003e07b  lea     rax, [rsp+0B8h+var_40]
0x18003e080  mov     qword ptr [rsp+0B8h+var_98], rax
0x18003e085  lea     rdx, dword_1800AF9B4
0x18003e08c  lea     rcx, dword_1800C1058
0x18003e093  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U3@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@35AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x18003e098  mov     [rsp+0B8h+var_98], 43h ; 'C'; unsigned int
0x18003e0a0  lea     r9, aOnecoreuapTerm_6; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18003e0a7  lea     r8, aRdpAvencRawCra_6; "Rdp::Avenc::Raw::CRawFrameProcessor<str"...
0x18003e0ae  lea     rdx, aRawframeproces_0; "RawFrameProcessorStart"
0x18003e0b5  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18003e0bc  call    ?push0@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1I@Z; Rdp::Modern::Utils::CInflightRecorder::push0(ushort const *,char const *,char const *,uint)
0x18003e0c1  mov     rax, [r14+8]
0x18003e0c5  mov     rcx, [rax+70h]
0x18003e0c9  mov     rsi, [rcx+1E0h]
0x18003e0d0  test    rsi, rsi
0x18003e0d3  jz      loc_18003E227
0x18003e0d9  mov     ecx, 0C08h; Size
0x18003e0de  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003e0e3  mov     rdi, rax
0x18003e0e6  mov     [rsp+0B8h+arg_8], rax
0x18003e0ee  mov     rdx, rsi; struct Rdp::Avenc::IFileIoChannel *
0x18003e0f1  mov     rcx, rax; this
0x18003e0f4  call    ??0CFcWireEncoderWithBulkCompressor@Avenc@Rdp@@QEAA@PEAUIFileIoChannel@12@PEAUIIoPacketCompleteEvents@12@@Z; Rdp::Avenc::CFcWireEncoderWithBulkCompressor::CFcWireEncoderWithBulkCompressor(Rdp::Avenc::IFileIoChannel *,Rdp::Avenc::IIoPacketCompleteEvents *)
0x18003e0f9  mov     dword ptr [rdi+0C00h], 0
0x18003e103  mov     [rsp+0B8h+arg_8], rdi
0x18003e10b  lea     rdi, [r14+18h]
0x18003e10f  lea     rdx, [rsp+0B8h+arg_8]
0x18003e117  mov     rcx, rdi
0x18003e11a  call    ??$?4U?$default_delete@V?$CRdpEgfx@VCFcWireEncoderWithBulkCompressor@Avenc@Rdp@@@Protocol@Rdp@@@std@@$0A@@?$unique_ptr@V?$CRdpEgfx@VCFcWireEncoderWithBulkCompressor@Avenc@Rdp@@@Protocol@Rdp@@U?$default_delete@V?$CRdpEgfx@VCFcWireEncoderWithBulkCompressor@Avenc@Rdp@@@Protocol@Rdp@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>>::operator=<std::default_delete<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>>,0>(std::unique_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>> &&)
0x18003e11f  lea     rcx, [rsp+0B8h+arg_8]
0x18003e127  call    ??1?$unique_ptr@V?$CRdpEgfx@VCFcWireEncoderWithBulkCompressor@Avenc@Rdp@@@Protocol@Rdp@@U?$default_delete@V?$CRdpEgfx@VCFcWireEncoderWithBulkCompressor@Avenc@Rdp@@@Protocol@Rdp@@@std@@@std@@QEAA@XZ; std::unique_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>>::~unique_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>>(void)
0x18003e12c  mov     edx, 1000h; unsigned __int64
0x18003e131  mov     rcx, [rdi]; this
0x18003e134  call    ?AllocatePool@CFcWireEncoderWithBulkCompressor@Avenc@Rdp@@QEAAX_K@Z; Rdp::Avenc::CFcWireEncoderWithBulkCompressor::AllocatePool(unsigned __int64)
0x18003e139  mov     rcx, [rdi]
0x18003e13c  mov     rax, [r14+8]
0x18003e140  mov     r12d, [rax+98h]
0x18003e147  mov     r13d, [rax+94h]
0x18003e14e  mov     eax, [rax+88h]
0x18003e154  mov     dword ptr [rsp+0B8h+arg_8], eax
0x18003e15b  xor     esi, esi
0x18003e15d  mov     rdx, [rcx+20h]
0x18003e161  mov     rax, [rcx+28h]
0x18003e165  sub     rax, rdx
0x18003e168  cmp     rax, 0Fh
0x18003e16c  jb      short loc_18003E17D
0x18003e16e  mov     rsi, [rcx+8]
0x18003e172  add     rsi, rdx
0x18003e175  lea     rax, [rdx+0Fh]
0x18003e179  mov     [rcx+20h], rax
0x18003e17d  mov     rcx, [rsp+0B8h]
0x18003e185  lea     rax, aUnableToEnsure_2; "Unable to ensure RDPGFX_CREATE_SURFACE_"...
0x18003e18c  mov     qword ptr [rsp+0B8h+var_90], rax
0x18003e191  mov     qword ptr [rsp+0B8h+var_98], rsi
0x18003e196  mov     r9d, 8007000Eh
0x18003e19c  lea     r8, aOnecoreuapTerm_14; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x18003e1a3  mov     edx, 10Ah
0x18003e1a8  call    ??$Throw_HrIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBDJ01ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(void *,uint,char const *,long,void *,char const *,...)
0x18003e1ad  mov     dword ptr [rsi], 9
0x18003e1b3  mov     dword ptr [rsi+4], 0Fh
0x18003e1ba  mov     eax, dword ptr [rsp+0B8h+arg_8]
0x18003e1c1  mov     [rsi+8], ax
0x18003e1c5  mov     [rsi+0Ah], r13w
0x18003e1ca  mov     [rsi+0Ch], r12w
0x18003e1cf  mov     byte ptr [rsi+0Eh], 21h ; '!'
0x18003e1d3  mov     rdx, [r14+8]
0x18003e1d7  mov     r9, [rdx+70h]
0x18003e1db  mov     eax, [rdx+90h]
0x18003e1e1  mov     dword ptr [rsp+0B8h+var_88], eax
0x18003e1e5  mov     eax, [rdx+8Ch]
0x18003e1eb  mov     [rsp+0B8h+var_90], eax; int
0x18003e1ef  mov     eax, [r9+0A8h]
0x18003e1f6  mov     [rsp+0B8h+var_98], eax; int
0x18003e1fa  mov     r9d, [r9+0A4h]
0x18003e201  mov     r8d, [rdx+88h]
0x18003e208  mov     dl, [rdx+0C8h]
0x18003e20e  mov     rcx, [rdi]
0x18003e211  call    ?MapSurfaceToOutput@?$CRdpEgfx@VCFcWireEncoderWithBulkCompressor@Avenc@Rdp@@@Protocol@Rdp@@QEAAX_NIHHHH@Z; Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>::MapSurfaceToOutput(bool,uint,int,int,int,int)
0x18003e216  xor     edx, edx; unsigned int
0x18003e218  mov     rcx, [rdi]; this
0x18003e21b  call    ?Flush@CFcWireEncoderWithBulkCompressor@Avenc@Rdp@@QEAAXI_N@Z; Rdp::Avenc::CFcWireEncoderWithBulkCompressor::Flush(uint,bool)
0x18003e220  lea     r12, WPP_RECORDER_INITIALIZED
0x18003e227  mov     rax, cs:WPP_GLOBAL_Control
0x18003e22e  lea     rcx, WPP_GLOBAL_Control
0x18003e235  cmp     rax, rcx
0x18003e238  jz      short loc_18003E245
0x18003e23a  test    [rax+1Ch], bl
0x18003e23d  jz      short loc_18003E245
0x18003e23f  cmp     byte ptr [rax+19h], 4
0x18003e243  jnb     short loc_18003E247
0x18003e245  xor     bl, bl
0x18003e247  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18003e24e  setnz   dil
0x18003e252  test    bl, bl
0x18003e254  jnz     short loc_18003E25B
0x18003e256  test    dil, dil
0x18003e259  jz      short loc_18003E28A
0x18003e25b  call    cs:__imp_GetCurrentThreadId
0x18003e261  mov     dword ptr [rsp+0B8h+var_78], eax; char
0x18003e265  mov     [rsp+0B8h+MessageGuid], r15; MessageGuid
0x18003e26a  mov     [rsp+0B8h+var_88], 0Bh; __int16
0x18003e271  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e278  mov     r9, [rcx+28h]; int
0x18003e27c  mov     r8b, dil; int
0x18003e27f  mov     dl, bl; int
0x18003e281  mov     rcx, [rcx+10h]; int
0x18003e285  call    WPP_RECORDER_AND_TRACE_SF_D
0x18003e28a  xor     eax, eax
0x18003e28c  jmp     short loc_18003E295
0x18003e28e  mov     eax, dword ptr [rsp+0B8h+arg_8]
0x18003e295  add     rsp, 80h
0x18003e29c  pop     r15
0x18003e29e  pop     r14
0x18003e2a0  pop     r13
0x18003e2a2  pop     r12
0x18003e2a4  pop     rdi
0x18003e2a5  pop     rsi
0x18003e2a6  pop     rbx
0x18003e2a7  retn
```
