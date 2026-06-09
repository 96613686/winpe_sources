# Rdp::Avenc::Raw::CRawFrameProcessor<Rdp::Avenc::ICpuFrameProcessor>::Stop(void)

- ea: `0x18003e660`
- end: `0x18003e9f5`
- name: `?Stop@?$CRawFrameProcessor@UICpuFrameProcessor@Avenc@Rdp@@@Raw@Avenc@Rdp@@UEAAJXZ`
- size: `917`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180002be0`
- `0x18001143c`
- `0x1800153f8`
- `0x180015480`
- `0x18003968c`
- `0x180039ff0`
- `0x18003e660`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003e6c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003e99f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003e6c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003e99f`

## string_xrefs

- `0x18003e923`: `onecoreuap\termsrv\rdp_bin\win\common/protocol/RdpEgfx/RdpEgfx.h`
- `0x18003e90c`: `Unable to ensure RDPGFX_DELETE_SURFACE_PDU_SIZE`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Rdp::Avenc::Raw::CRawFrameProcessor<Rdp::Avenc::ICpuFrameProcessor>::Stop(
        __int64 a1,
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
  const char *v12; // r9
  Rdp::Avenc::CFcWireEncoderWithBulkCompressor *v13; // rcx
  _QWORD *v14; // rcx
  int v15; // edi
  __int64 v16; // rbx
  __int64 v17; // rdx
  bool v18; // r8
  __int64 v19; // rcx
  bool v20; // bl
  char v21; // al
  int v22; // r8d
  int v23; // edx
  __int64 result; // rax
  int v25; // [rsp+20h] [rbp-B8h]
  int v26; // [rsp+20h] [rbp-B8h]
  int v27; // [rsp+28h] [rbp-B0h]
  int v28; // [rsp+28h] [rbp-B0h]
  const char *v29; // [rsp+80h] [rbp-58h] BYREF
  __int64 v30; // [rsp+88h] [rbp-50h] BYREF
  const char *v31; // [rsp+90h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]
  int v33; // [rsp+E0h] [rbp+8h] BYREF
  __int64 v34; // [rsp+E8h] [rbp+10h] BYREF
  const char *v35; // [rsp+F0h] [rbp+18h] BYREF
  int *v36; // [rsp+F8h] [rbp+20h] BYREF

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
      v25,
      v27,
      12,
      &WPP_4305ebc2891e3311ffa3fc8a7ac47271_Traceguids,
      CurrentThreadId);
  }
  if ( (unsigned int)dword_1800C1058 > 4
    && (qword_1800C1068 & 0x470000000000LL) != 0
    && (qword_1800C1070 & 0x470000000000LL) == qword_1800C1070 )
  {
    v11 = *(_QWORD *)(a1 + 8);
    v34 = v11 + 120;
    v33 = *(_DWORD *)(*(_QWORD *)(v11 + 112) + 160LL);
    v35 = "Stop Raw frame processor";
    v36 = &xmmword_1800C21A0;
    v29 = "RdpAvenc";
    v30 = 0x1000000;
    v31 = "Checkpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
      (unsigned int)&dword_1800C1058,
      (unsigned int)qword_1800AFA20,
      a3,
      a4,
      (__int64)&v31,
      (__int64)&v30,
      (__int64)&v29,
      (__int64)&v36,
      (__int64)&v35,
      (__int64)&v33,
      (__int64)&v34);
  }
  v28 = *(_DWORD *)(*(_QWORD *)(a1 + 8) + 120LL);
  try
  {
    Rdp::Modern::Utils::CInflightRecorder::pushN(
      (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      (wchar_t *)L"RawFrameProcessorStop: Id {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}",
      "Rdp::Avenc::Raw::CRawFrameProcessor<struct Rdp::Avenc::ICpuFrameProcessor>::Stop",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rawprocessor\\rawframeprocessor.cpp",
      0x8Au);
    v13 = *(Rdp::Avenc::CFcWireEncoderWithBulkCompressor **)(a1 + 24);
    if ( v13 )
    {
      Rdp::Avenc::CFcWireEncoderWithBulkCompressor::AllocatePool(v13, 0x1000u);
      v14 = *(_QWORD **)(a1 + 24);
      v15 = *(_DWORD *)(*(_QWORD *)(a1 + 8) + 136LL);
      v16 = 0;
      v17 = v14[4];
      if ( (unsigned __int64)(v14[5] - v17) >= 0xA )
      {
        v16 = v17 + v14[1];
        v14[4] = v17 + 10;
      }
      wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(
        retaddr,
        343,
        "onecoreuap\\termsrv\\rdp_bin\\win\\common/protocol/RdpEgfx/RdpEgfx.h",
        2147942414LL,
        v16,
        "Unable to ensure RDPGFX_DELETE_SURFACE_PDU_SIZE");
      *(_DWORD *)v16 = 10;
      *(_DWORD *)(v16 + 4) = 10;
      *(_WORD *)(v16 + 8) = v15;
      Rdp::Avenc::CFcWireEncoderWithBulkCompressor::Flush(
        *(Rdp::Avenc::CFcWireEncoderWithBulkCompressor **)(a1 + 24),
        0,
        v18);
    }
    v19 = *(_QWORD *)(a1 + 8);
    *(_QWORD *)(a1 + 8) = 0;
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v5 = 0;
    }
    v20 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v21 = GetCurrentThreadId();
      LOBYTE(v22) = v20;
      LOBYTE(v23) = v5;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v23,
        v22,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v26,
        v28,
        13,
        &WPP_4305ebc2891e3311ffa3fc8a7ac47271_Traceguids,
        v21);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x9D,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rawprocessor\\rawframeprocessor.cpp",
                           v12);
  }
  return result;
}

```

## disassembly

```asm
0x18003e660  push    rbx
0x18003e662  push    rsi
0x18003e663  push    rdi
0x18003e664  push    r12
0x18003e666  push    r13
0x18003e668  push    r14
0x18003e66a  push    r15
0x18003e66c  sub     rsp, 0A0h
0x18003e673  mov     r13, rcx
0x18003e676  lea     rcx, WPP_GLOBAL_Control
0x18003e67d  mov     rax, cs:WPP_GLOBAL_Control
0x18003e684  mov     r12b, 1
0x18003e687  cmp     rax, rcx
0x18003e68a  jz      short loc_18003E6A0
0x18003e68c  test    [rax+1Ch], r12b
0x18003e690  jz      short loc_18003E6A0
0x18003e692  cmp     byte ptr [rax+19h], 4
0x18003e696  jb      short loc_18003E6A0
0x18003e698  mov     bl, r12b
0x18003e69b  xor     r15d, r15d
0x18003e69e  jmp     short loc_18003E6A6
0x18003e6a0  xor     r15d, r15d
0x18003e6a3  mov     bl, r15b
0x18003e6a6  lea     rax, WPP_RECORDER_INITIALIZED
0x18003e6ad  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18003e6b4  setnz   dil
0x18003e6b8  test    bl, bl
0x18003e6ba  jnz     short loc_18003E6C1
0x18003e6bc  test    dil, dil
0x18003e6bf  jz      short loc_18003E6F7
0x18003e6c1  call    cs:__imp_GetCurrentThreadId
0x18003e6c7  mov     dword ptr [rsp+0D8h+var_98], eax; char
0x18003e6cb  lea     rsi, WPP_4305ebc2891e3311ffa3fc8a7ac47271_Traceguids
0x18003e6d2  mov     [rsp+0D8h+MessageGuid], rsi; MessageGuid
0x18003e6d7  mov     [rsp+0D8h+var_A8], 0Ch; __int16
0x18003e6de  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e6e5  mov     r9, [rcx+28h]; int
0x18003e6e9  mov     r8b, dil; int
0x18003e6ec  mov     dl, bl; int
0x18003e6ee  mov     rcx, [rcx+10h]; int
0x18003e6f2  call    WPP_RECORDER_AND_TRACE_SF_D
0x18003e6f7  mov     eax, cs:dword_1800C1058
0x18003e6fd  cmp     eax, 4
0x18003e700  jbe     loc_18003E80D
0x18003e706  mov     rcx, cs:qword_1800C1070
0x18003e70d  mov     rax, cs:qword_1800C1068
0x18003e714  mov     rdx, 470000000000h
0x18003e71e  test    rdx, rax
0x18003e721  jz      loc_18003E80D
0x18003e727  mov     rax, rcx
0x18003e72a  and     rax, rdx
0x18003e72d  cmp     rax, rcx
0x18003e730  jnz     loc_18003E80D
0x18003e736  mov     rcx, [r13+8]
0x18003e73a  lea     rax, [rcx+78h]
0x18003e73e  mov     [rsp+0D8h+arg_8], rax
0x18003e746  mov     rax, [rcx+70h]
0x18003e74a  mov     ecx, [rax+0A0h]
0x18003e750  mov     [rsp+0D8h+arg_0], ecx
0x18003e757  lea     rax, aStopRawFramePr; "Stop Raw frame processor"
0x18003e75e  mov     [rsp+0D8h+arg_10], rax
0x18003e766  lea     rax, xmmword_1800C21A0
0x18003e76d  mov     [rsp+0D8h+arg_18], rax
0x18003e775  lea     rax, aRdpavenc; "RdpAvenc"
0x18003e77c  mov     [rsp+0D8h+var_58], rax
0x18003e784  mov     [rsp+0D8h+var_50], 1000000h
0x18003e790  lea     rax, aCheckpoint; "Checkpoint"
0x18003e797  mov     [rsp+0D8h+var_48], rax
0x18003e79f  lea     rax, [rsp+0D8h+arg_8]
0x18003e7a7  mov     [rsp+0D8h+var_88], rax
0x18003e7ac  lea     rax, [rsp+0D8h+arg_0]
0x18003e7b4  mov     [rsp+0D8h+var_90], rax
0x18003e7b9  lea     rax, [rsp+0D8h+arg_10]
0x18003e7c1  mov     qword ptr [rsp+0D8h+var_98], rax
0x18003e7c6  lea     rax, [rsp+0D8h+arg_18]
0x18003e7ce  mov     [rsp+0D8h+MessageGuid], rax
0x18003e7d3  lea     rax, [rsp+0D8h+var_58]
0x18003e7db  mov     qword ptr [rsp+0D8h+var_A8], rax
0x18003e7e0  lea     rax, [rsp+0D8h+var_50]
0x18003e7e8  mov     qword ptr [rsp+0D8h+var_B0], rax
0x18003e7ed  lea     rax, [rsp+0D8h+var_48]
0x18003e7f5  mov     qword ptr [rsp+0D8h+var_B8], rax
0x18003e7fa  lea     rdx, qword_1800AFA20
0x18003e801  lea     rcx, dword_1800C1058
0x18003e808  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x18003e80d  mov     r14, [r13+8]
0x18003e811  movzx   eax, byte ptr [r14+87h]
0x18003e819  movzx   ecx, byte ptr [r14+86h]
0x18003e821  movzx   edx, byte ptr [r14+85h]
0x18003e829  movzx   r8d, byte ptr [r14+84h]
0x18003e831  movzx   r9d, byte ptr [r14+83h]
0x18003e839  movzx   r10d, byte ptr [r14+82h]
0x18003e841  movzx   r11d, byte ptr [r14+81h]
0x18003e849  movzx   ebx, byte ptr [r14+80h]
0x18003e851  movzx   edi, word ptr [r14+7Eh]
0x18003e856  movzx   esi, word ptr [r14+7Ch]
0x18003e85b  mov     [rsp+0D8h+var_60], eax
0x18003e85f  mov     [rsp+0D8h+var_68], ecx
0x18003e863  mov     [rsp+0D8h+var_70], edx
0x18003e867  mov     [rsp+0D8h+var_78], r8d
0x18003e86c  mov     [rsp+0D8h+var_80], r9d
0x18003e871  mov     dword ptr [rsp+0D8h+var_88], r10d
0x18003e876  mov     dword ptr [rsp+0D8h+var_90], r11d
0x18003e87b  mov     dword ptr [rsp+0D8h+var_98], ebx
0x18003e87f  mov     dword ptr [rsp+0D8h+MessageGuid], edi
0x18003e883  mov     dword ptr [rsp+0D8h+var_A8], esi
0x18003e887  mov     eax, [r14+78h]
0x18003e88b  mov     [rsp+0D8h+var_B0], eax
0x18003e88f  mov     [rsp+0D8h+var_B8], 8Ah; unsigned int
0x18003e897  lea     r9, aOnecoreuapTerm_6; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18003e89e  lea     r8, aRdpAvencRawCra_2; "Rdp::Avenc::Raw::CRawFrameProcessor<str"...
0x18003e8a5  lea     rdx, aRawframeproces; "RawFrameProcessorStop: Id {%08lX-%04hX-"...
0x18003e8ac  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18003e8b3  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18003e8b8  mov     rcx, [r13+18h]; this
0x18003e8bc  test    rcx, rcx
0x18003e8bf  jz      loc_18003E949
0x18003e8c5  mov     edx, 1000h; unsigned __int64
0x18003e8ca  call    ?AllocatePool@CFcWireEncoderWithBulkCompressor@Avenc@Rdp@@QEAAX_K@Z; Rdp::Avenc::CFcWireEncoderWithBulkCompressor::AllocatePool(unsigned __int64)
0x18003e8cf  mov     rcx, [r13+18h]
0x18003e8d3  mov     rax, [r13+8]
0x18003e8d7  mov     edi, [rax+88h]
0x18003e8dd  mov     rbx, r15
0x18003e8e0  mov     rdx, [rcx+20h]
0x18003e8e4  mov     rax, [rcx+28h]
0x18003e8e8  sub     rax, rdx
0x18003e8eb  mov     esi, 0Ah
0x18003e8f0  cmp     rax, rsi
0x18003e8f3  jb      short loc_18003E904
0x18003e8f5  mov     rbx, [rcx+8]
0x18003e8f9  add     rbx, rdx
0x18003e8fc  lea     rax, [rdx+0Ah]
0x18003e900  mov     [rcx+20h], rax
0x18003e904  mov     rcx, [rsp+0D8h]
0x18003e90c  lea     rax, aUnableToEnsure_20; "Unable to ensure RDPGFX_DELETE_SURFACE_"...
0x18003e913  mov     qword ptr [rsp+0D8h+var_B0], rax; int
0x18003e918  mov     qword ptr [rsp+0D8h+var_B8], rbx; int
0x18003e91d  mov     r9d, 8007000Eh
0x18003e923  lea     r8, aOnecoreuapTerm_14; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x18003e92a  mov     edx, 157h
0x18003e92f  call    ??$Throw_HrIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBDJ01ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(void *,uint,char const *,long,void *,char const *,...)
0x18003e934  mov     [rbx], esi
0x18003e936  mov     [rbx+4], esi
0x18003e939  mov     [rbx+8], di
0x18003e93d  xor     edx, edx; unsigned int
0x18003e93f  mov     rcx, [r13+18h]; this
0x18003e943  call    ?Flush@CFcWireEncoderWithBulkCompressor@Avenc@Rdp@@QEAAXI_N@Z; Rdp::Avenc::CFcWireEncoderWithBulkCompressor::Flush(uint,bool)
0x18003e948  nop
0x18003e949  mov     rcx, [r13+8]
0x18003e94d  mov     [r13+8], r15
0x18003e951  test    rcx, rcx
0x18003e954  jz      short loc_18003E963
0x18003e956  mov     rax, [rcx]
0x18003e959  mov     rax, [rax+10h]
0x18003e95d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e962  nop
0x18003e963  mov     rax, cs:WPP_GLOBAL_Control
0x18003e96a  lea     rcx, WPP_GLOBAL_Control
0x18003e971  cmp     rax, rcx
0x18003e974  jz      short loc_18003E982
0x18003e976  test    [rax+1Ch], r12b
0x18003e97a  jz      short loc_18003E982
0x18003e97c  cmp     byte ptr [rax+19h], 4
0x18003e980  jnb     short loc_18003E985
0x18003e982  mov     r12b, r15b
0x18003e985  lea     rax, WPP_RECORDER_INITIALIZED
0x18003e98c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18003e993  setnz   bl
0x18003e996  test    r12b, r12b
0x18003e999  jnz     short loc_18003E99F
0x18003e99b  test    bl, bl
0x18003e99d  jz      short loc_18003E9D6
0x18003e99f  call    cs:__imp_GetCurrentThreadId
0x18003e9a5  mov     dword ptr [rsp+0D8h+var_98], eax; char
0x18003e9a9  lea     rax, WPP_4305ebc2891e3311ffa3fc8a7ac47271_Traceguids
0x18003e9b0  mov     [rsp+0D8h+MessageGuid], rax; MessageGuid
0x18003e9b5  mov     [rsp+0D8h+var_A8], 0Dh; __int16
0x18003e9bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e9c3  mov     r9, [rcx+28h]; int
0x18003e9c7  mov     r8b, bl; int
0x18003e9ca  mov     dl, r12b; int
0x18003e9cd  mov     rcx, [rcx+10h]; int
0x18003e9d1  call    WPP_RECORDER_AND_TRACE_SF_D
0x18003e9d6  xor     eax, eax
0x18003e9d8  jmp     short loc_18003E9E1
0x18003e9da  mov     eax, [rsp+0D8h+arg_0]
0x18003e9e1  add     rsp, 0A0h
0x18003e9e8  pop     r15
0x18003e9ea  pop     r14
0x18003e9ec  pop     r13
0x18003e9ee  pop     r12
0x18003e9f0  pop     rdi
0x18003e9f1  pop     rsi
0x18003e9f2  pop     rbx
0x18003e9f3  retn
```
