# Rdp::Avenc::Raw::CRawFrameProcessor<Rdp::Avenc::IGpuFrameProcessor>::Stop(void)

- ea: `0x18003ea00`
- end: `0x18003ed95`
- name: `?Stop@?$CRawFrameProcessor@UIGpuFrameProcessor@Avenc@Rdp@@@Raw@Avenc@Rdp@@UEAAJXZ`
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
- `0x18003ea00`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003ea61`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003ed3f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003ea61`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003ed3f`

## string_xrefs

- `0x18003ecc3`: `onecoreuap\termsrv\rdp_bin\win\common/protocol/RdpEgfx/RdpEgfx.h`
- `0x18003ecac`: `Unable to ensure RDPGFX_DELETE_SURFACE_PDU_SIZE`

## pseudocode

```c
__int64 __fastcall Rdp::Avenc::Raw::CRawFrameProcessor<Rdp::Avenc::IGpuFrameProcessor>::Stop(
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
  Rdp::Avenc::CFcWireEncoderWithBulkCompressor *v12; // rcx
  _QWORD *v13; // rcx
  int v14; // edi
  __int64 v15; // rbx
  __int64 v16; // rdx
  bool v17; // r8
  __int64 v18; // rcx
  bool v19; // bl
  char v20; // al
  int v21; // r8d
  int v22; // edx
  int v24; // [rsp+20h] [rbp-B8h]
  int v25; // [rsp+20h] [rbp-B8h]
  int v26; // [rsp+28h] [rbp-B0h]
  int v27; // [rsp+28h] [rbp-B0h]
  const char *v28; // [rsp+80h] [rbp-58h] BYREF
  __int64 v29; // [rsp+88h] [rbp-50h] BYREF
  const char *v30; // [rsp+90h] [rbp-48h] BYREF
  void *retaddr; // [rsp+D8h] [rbp+0h]
  int v32; // [rsp+E0h] [rbp+8h] BYREF
  __int64 v33; // [rsp+E8h] [rbp+10h] BYREF
  const char *v34; // [rsp+F0h] [rbp+18h] BYREF
  int *v35; // [rsp+F8h] [rbp+20h] BYREF

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
      v24,
      v26,
      12,
      &WPP_4305ebc2891e3311ffa3fc8a7ac47271_Traceguids,
      CurrentThreadId);
  }
  if ( (unsigned int)dword_1800C1058 > 4
    && (qword_1800C1068 & 0x470000000000LL) != 0
    && (qword_1800C1070 & 0x470000000000LL) == qword_1800C1070 )
  {
    v11 = *(_QWORD *)(a1 + 8);
    v33 = v11 + 120;
    v32 = *(_DWORD *)(*(_QWORD *)(v11 + 112) + 160LL);
    v34 = "Stop Raw frame processor";
    v35 = &xmmword_1800C21A0;
    v28 = "RdpAvenc";
    v29 = 0x1000000;
    v30 = "Checkpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
      (unsigned int)&dword_1800C1058,
      (unsigned int)byte_1800AFA8B,
      a3,
      a4,
      (__int64)&v30,
      (__int64)&v29,
      (__int64)&v28,
      (__int64)&v35,
      (__int64)&v34,
      (__int64)&v32,
      (__int64)&v33);
  }
  v27 = *(_DWORD *)(*(_QWORD *)(a1 + 8) + 120LL);
  Rdp::Modern::Utils::CInflightRecorder::pushN(
    (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
    (wchar_t *)L"RawFrameProcessorStop: Id {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}",
    "Rdp::Avenc::Raw::CRawFrameProcessor<struct Rdp::Avenc::IGpuFrameProcessor>::Stop",
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rawprocessor\\rawframeprocessor.cpp",
    0x8Au);
  v12 = *(Rdp::Avenc::CFcWireEncoderWithBulkCompressor **)(a1 + 24);
  if ( v12 )
  {
    Rdp::Avenc::CFcWireEncoderWithBulkCompressor::AllocatePool(v12, 0x1000u);
    v13 = *(_QWORD **)(a1 + 24);
    v14 = *(_DWORD *)(*(_QWORD *)(a1 + 8) + 136LL);
    v15 = 0;
    v16 = v13[4];
    if ( (unsigned __int64)(v13[5] - v16) >= 0xA )
    {
      v15 = v16 + v13[1];
      v13[4] = v16 + 10;
    }
    wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(
      retaddr,
      343,
      "onecoreuap\\termsrv\\rdp_bin\\win\\common/protocol/RdpEgfx/RdpEgfx.h",
      2147942414LL,
      v15,
      "Unable to ensure RDPGFX_DELETE_SURFACE_PDU_SIZE");
    *(_DWORD *)v15 = 10;
    *(_DWORD *)(v15 + 4) = 10;
    *(_WORD *)(v15 + 8) = v14;
    Rdp::Avenc::CFcWireEncoderWithBulkCompressor::Flush(
      *(Rdp::Avenc::CFcWireEncoderWithBulkCompressor **)(a1 + 24),
      0,
      v17);
  }
  v18 = *(_QWORD *)(a1 + 8);
  *(_QWORD *)(a1 + 8) = 0;
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
  {
    v5 = 0;
  }
  v19 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v20 = GetCurrentThreadId();
    LOBYTE(v21) = v19;
    LOBYTE(v22) = v5;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v22,
      v21,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v25,
      v27,
      13,
      &WPP_4305ebc2891e3311ffa3fc8a7ac47271_Traceguids,
      v20);
  }
  return 0;
}

```

## disassembly

```asm
0x18003ea00  push    rbx
0x18003ea02  push    rsi
0x18003ea03  push    rdi
0x18003ea04  push    r12
0x18003ea06  push    r13
0x18003ea08  push    r14
0x18003ea0a  push    r15
0x18003ea0c  sub     rsp, 0A0h
0x18003ea13  mov     r13, rcx
0x18003ea16  lea     rcx, WPP_GLOBAL_Control
0x18003ea1d  mov     rax, cs:WPP_GLOBAL_Control
0x18003ea24  mov     r12b, 1
0x18003ea27  cmp     rax, rcx
0x18003ea2a  jz      short loc_18003EA40
0x18003ea2c  test    [rax+1Ch], r12b
0x18003ea30  jz      short loc_18003EA40
0x18003ea32  cmp     byte ptr [rax+19h], 4
0x18003ea36  jb      short loc_18003EA40
0x18003ea38  mov     bl, r12b
0x18003ea3b  xor     r15d, r15d
0x18003ea3e  jmp     short loc_18003EA46
0x18003ea40  xor     r15d, r15d
0x18003ea43  mov     bl, r15b
0x18003ea46  lea     rax, WPP_RECORDER_INITIALIZED
0x18003ea4d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18003ea54  setnz   dil
0x18003ea58  test    bl, bl
0x18003ea5a  jnz     short loc_18003EA61
0x18003ea5c  test    dil, dil
0x18003ea5f  jz      short loc_18003EA97
0x18003ea61  call    cs:__imp_GetCurrentThreadId
0x18003ea67  mov     dword ptr [rsp+0D8h+var_98], eax; char
0x18003ea6b  lea     rsi, WPP_4305ebc2891e3311ffa3fc8a7ac47271_Traceguids
0x18003ea72  mov     [rsp+0D8h+MessageGuid], rsi; MessageGuid
0x18003ea77  mov     [rsp+0D8h+var_A8], 0Ch; __int16
0x18003ea7e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ea85  mov     r9, [rcx+28h]; int
0x18003ea89  mov     r8b, dil; int
0x18003ea8c  mov     dl, bl; int
0x18003ea8e  mov     rcx, [rcx+10h]; int
0x18003ea92  call    WPP_RECORDER_AND_TRACE_SF_D
0x18003ea97  mov     eax, cs:dword_1800C1058
0x18003ea9d  cmp     eax, 4
0x18003eaa0  jbe     loc_18003EBAD
0x18003eaa6  mov     rcx, cs:qword_1800C1070
0x18003eaad  mov     rax, cs:qword_1800C1068
0x18003eab4  mov     rdx, 470000000000h
0x18003eabe  test    rdx, rax
0x18003eac1  jz      loc_18003EBAD
0x18003eac7  mov     rax, rcx
0x18003eaca  and     rax, rdx
0x18003eacd  cmp     rax, rcx
0x18003ead0  jnz     loc_18003EBAD
0x18003ead6  mov     rcx, [r13+8]
0x18003eada  lea     rax, [rcx+78h]
0x18003eade  mov     [rsp+0D8h+arg_8], rax
0x18003eae6  mov     rax, [rcx+70h]
0x18003eaea  mov     ecx, [rax+0A0h]
0x18003eaf0  mov     [rsp+0D8h+arg_0], ecx
0x18003eaf7  lea     rax, aStopRawFramePr; "Stop Raw frame processor"
0x18003eafe  mov     [rsp+0D8h+arg_10], rax
0x18003eb06  lea     rax, xmmword_1800C21A0
0x18003eb0d  mov     [rsp+0D8h+arg_18], rax
0x18003eb15  lea     rax, aRdpavenc; "RdpAvenc"
0x18003eb1c  mov     [rsp+0D8h+var_58], rax
0x18003eb24  mov     [rsp+0D8h+var_50], 1000000h
0x18003eb30  lea     rax, aCheckpoint; "Checkpoint"
0x18003eb37  mov     [rsp+0D8h+var_48], rax
0x18003eb3f  lea     rax, [rsp+0D8h+arg_8]
0x18003eb47  mov     [rsp+0D8h+var_88], rax
0x18003eb4c  lea     rax, [rsp+0D8h+arg_0]
0x18003eb54  mov     [rsp+0D8h+var_90], rax
0x18003eb59  lea     rax, [rsp+0D8h+arg_10]
0x18003eb61  mov     qword ptr [rsp+0D8h+var_98], rax
0x18003eb66  lea     rax, [rsp+0D8h+arg_18]
0x18003eb6e  mov     [rsp+0D8h+MessageGuid], rax
0x18003eb73  lea     rax, [rsp+0D8h+var_58]
0x18003eb7b  mov     qword ptr [rsp+0D8h+var_A8], rax
0x18003eb80  lea     rax, [rsp+0D8h+var_50]
0x18003eb88  mov     qword ptr [rsp+0D8h+var_B0], rax
0x18003eb8d  lea     rax, [rsp+0D8h+var_48]
0x18003eb95  mov     qword ptr [rsp+0D8h+var_B8], rax
0x18003eb9a  lea     rdx, byte_1800AFA8B
0x18003eba1  lea     rcx, dword_1800C1058
0x18003eba8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x18003ebad  mov     r14, [r13+8]
0x18003ebb1  movzx   eax, byte ptr [r14+87h]
0x18003ebb9  movzx   ecx, byte ptr [r14+86h]
0x18003ebc1  movzx   edx, byte ptr [r14+85h]
0x18003ebc9  movzx   r8d, byte ptr [r14+84h]
0x18003ebd1  movzx   r9d, byte ptr [r14+83h]
0x18003ebd9  movzx   r10d, byte ptr [r14+82h]
0x18003ebe1  movzx   r11d, byte ptr [r14+81h]
0x18003ebe9  movzx   ebx, byte ptr [r14+80h]
0x18003ebf1  movzx   edi, word ptr [r14+7Eh]
0x18003ebf6  movzx   esi, word ptr [r14+7Ch]
0x18003ebfb  mov     [rsp+0D8h+var_60], eax
0x18003ebff  mov     [rsp+0D8h+var_68], ecx
0x18003ec03  mov     [rsp+0D8h+var_70], edx
0x18003ec07  mov     [rsp+0D8h+var_78], r8d
0x18003ec0c  mov     [rsp+0D8h+var_80], r9d
0x18003ec11  mov     dword ptr [rsp+0D8h+var_88], r10d
0x18003ec16  mov     dword ptr [rsp+0D8h+var_90], r11d
0x18003ec1b  mov     dword ptr [rsp+0D8h+var_98], ebx
0x18003ec1f  mov     dword ptr [rsp+0D8h+MessageGuid], edi
0x18003ec23  mov     dword ptr [rsp+0D8h+var_A8], esi
0x18003ec27  mov     eax, [r14+78h]
0x18003ec2b  mov     [rsp+0D8h+var_B0], eax
0x18003ec2f  mov     [rsp+0D8h+var_B8], 8Ah; unsigned int
0x18003ec37  lea     r9, aOnecoreuapTerm_6; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18003ec3e  lea     r8, aRdpAvencRawCra_4; "Rdp::Avenc::Raw::CRawFrameProcessor<str"...
0x18003ec45  lea     rdx, aRawframeproces; "RawFrameProcessorStop: Id {%08lX-%04hX-"...
0x18003ec4c  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18003ec53  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18003ec58  mov     rcx, [r13+18h]; this
0x18003ec5c  test    rcx, rcx
0x18003ec5f  jz      loc_18003ECE9
0x18003ec65  mov     edx, 1000h; unsigned __int64
0x18003ec6a  call    ?AllocatePool@CFcWireEncoderWithBulkCompressor@Avenc@Rdp@@QEAAX_K@Z; Rdp::Avenc::CFcWireEncoderWithBulkCompressor::AllocatePool(unsigned __int64)
0x18003ec6f  mov     rcx, [r13+18h]
0x18003ec73  mov     rax, [r13+8]
0x18003ec77  mov     edi, [rax+88h]
0x18003ec7d  mov     rbx, r15
0x18003ec80  mov     rdx, [rcx+20h]
0x18003ec84  mov     rax, [rcx+28h]
0x18003ec88  sub     rax, rdx
0x18003ec8b  mov     esi, 0Ah
0x18003ec90  cmp     rax, rsi
0x18003ec93  jb      short loc_18003ECA4
0x18003ec95  mov     rbx, [rcx+8]
0x18003ec99  add     rbx, rdx
0x18003ec9c  lea     rax, [rdx+0Ah]
0x18003eca0  mov     [rcx+20h], rax
0x18003eca4  mov     rcx, [rsp+0D8h]
0x18003ecac  lea     rax, aUnableToEnsure_20; "Unable to ensure RDPGFX_DELETE_SURFACE_"...
0x18003ecb3  mov     qword ptr [rsp+0D8h+var_B0], rax; int
0x18003ecb8  mov     qword ptr [rsp+0D8h+var_B8], rbx; int
0x18003ecbd  mov     r9d, 8007000Eh
0x18003ecc3  lea     r8, aOnecoreuapTerm_14; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x18003ecca  mov     edx, 157h
0x18003eccf  call    ??$Throw_HrIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBDJ01ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(void *,uint,char const *,long,void *,char const *,...)
0x18003ecd4  mov     [rbx], esi
0x18003ecd6  mov     [rbx+4], esi
0x18003ecd9  mov     [rbx+8], di
0x18003ecdd  xor     edx, edx; unsigned int
0x18003ecdf  mov     rcx, [r13+18h]; this
0x18003ece3  call    ?Flush@CFcWireEncoderWithBulkCompressor@Avenc@Rdp@@QEAAXI_N@Z; Rdp::Avenc::CFcWireEncoderWithBulkCompressor::Flush(uint,bool)
0x18003ece8  nop
0x18003ece9  mov     rcx, [r13+8]
0x18003eced  mov     [r13+8], r15
0x18003ecf1  test    rcx, rcx
0x18003ecf4  jz      short loc_18003ED03
0x18003ecf6  mov     rax, [rcx]
0x18003ecf9  mov     rax, [rax+10h]
0x18003ecfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ed02  nop
0x18003ed03  mov     rax, cs:WPP_GLOBAL_Control
0x18003ed0a  lea     rcx, WPP_GLOBAL_Control
0x18003ed11  cmp     rax, rcx
0x18003ed14  jz      short loc_18003ED22
0x18003ed16  test    [rax+1Ch], r12b
0x18003ed1a  jz      short loc_18003ED22
0x18003ed1c  cmp     byte ptr [rax+19h], 4
0x18003ed20  jnb     short loc_18003ED25
0x18003ed22  mov     r12b, r15b
0x18003ed25  lea     rax, WPP_RECORDER_INITIALIZED
0x18003ed2c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18003ed33  setnz   bl
0x18003ed36  test    r12b, r12b
0x18003ed39  jnz     short loc_18003ED3F
0x18003ed3b  test    bl, bl
0x18003ed3d  jz      short loc_18003ED76
0x18003ed3f  call    cs:__imp_GetCurrentThreadId
0x18003ed45  mov     dword ptr [rsp+0D8h+var_98], eax; char
0x18003ed49  lea     rax, WPP_4305ebc2891e3311ffa3fc8a7ac47271_Traceguids
0x18003ed50  mov     [rsp+0D8h+MessageGuid], rax; MessageGuid
0x18003ed55  mov     [rsp+0D8h+var_A8], 0Dh; __int16
0x18003ed5c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ed63  mov     r9, [rcx+28h]; int
0x18003ed67  mov     r8b, bl; int
0x18003ed6a  mov     dl, r12b; int
0x18003ed6d  mov     rcx, [rcx+10h]; int
0x18003ed71  call    WPP_RECORDER_AND_TRACE_SF_D
0x18003ed76  xor     eax, eax
0x18003ed78  jmp     short loc_18003ED81
0x18003ed7a  mov     eax, [rsp+0D8h+arg_0]
0x18003ed81  add     rsp, 0A0h
0x18003ed88  pop     r15
0x18003ed8a  pop     r14
0x18003ed8c  pop     r13
0x18003ed8e  pop     r12
0x18003ed90  pop     rdi
0x18003ed91  pop     rsi
0x18003ed92  pop     rbx
0x18003ed93  retn
```
