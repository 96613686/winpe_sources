# Rdp::Avenc::Hevc::CHevcFrameProcessor::Stop(void)

- ea: `0x18002d3a0`
- end: `0x18002d83e`
- name: `?Stop@CHevcFrameProcessor@Hevc@Avenc@Rdp@@UEAAJXZ`
- size: `1182`
- prototype: `__int64 __fastcall(Rdp::Avenc::Hevc::CHevcFrameProcessor *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180029060`

## callees

- `0x180002be0`
- `0x18001143c`
- `0x1800153f8`
- `0x180015480`
- `0x180022fb8`
- `0x180023b34`
- `0x180023ee4`
- `0x18002d3a0`
- `0x18002dd40`
- `0x18002e0c4`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d404`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d7b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d404`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d7b3`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18002d691`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18002d691`

## string_xrefs

- `0x18002d712`: `onecoreuap\termsrv\rdp_bin\win\common/protocol/RdpEgfx/RdpEgfx.h`
- `0x18002d6fb`: `Unable to ensure RDPGFX_DELETE_SURFACE_PDU_SIZE`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Rdp::Avenc::Hevc::CHevcFrameProcessor::Stop(
        Rdp::Avenc::Hevc::CHevcFrameProcessor *this,
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
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rax
  volatile signed __int32 *v17; // rbx
  Rdp::Avenc::CFcWireEncoderWithBulkUncompressed *v18; // rsi
  const char *v19; // r9
  int v20; // r13d
  _DWORD *v21; // rdi
  unsigned int v22; // edx
  __int64 *v23; // r14
  __int64 v24; // rcx
  bool v25; // di
  char v26; // al
  int v27; // r8d
  int v28; // edx
  __int64 result; // rax
  int v30; // [rsp+20h] [rbp-C8h]
  int v31; // [rsp+20h] [rbp-C8h]
  int v32; // [rsp+28h] [rbp-C0h]
  int v33; // [rsp+28h] [rbp-C0h]
  const char *v34; // [rsp+80h] [rbp-68h] BYREF
  __int128 v35; // [rsp+88h] [rbp-60h] BYREF
  _QWORD v36[10]; // [rsp+98h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]
  char *v38; // [rsp+F0h] [rbp+8h] BYREF
  volatile signed __int32 *v39; // [rsp+F8h] [rbp+10h] BYREF
  const char *v40; // [rsp+100h] [rbp+18h] BYREF
  int *v41; // [rsp+108h] [rbp+20h] BYREF

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
      v30,
      v32,
      12,
      &WPP_bc0801f283643948a642b8834c5cca7a_Traceguids,
      CurrentThreadId);
  }
  if ( (unsigned int)dword_1800C1058 > 4
    && (qword_1800C1068 & 0x470000000000LL) != 0
    && (qword_1800C1070 & 0x470000000000LL) == qword_1800C1070 )
  {
    v11 = *((_QWORD *)this + 7);
    v39 = (volatile signed __int32 *)(v11 + 120);
    LODWORD(v38) = *(_DWORD *)(*(_QWORD *)(v11 + 112) + 160LL);
    v40 = "Stop Hevc frame processor";
    v41 = &xmmword_1800C21A0;
    v34 = "RdpAvenc";
    *(_QWORD *)&v35 = 0x1000000;
    v36[0] = "Checkpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
      (unsigned int)&dword_1800C1058,
      (unsigned int)word_1800AE7A2,
      a3,
      a4,
      (__int64)v36,
      (__int64)&v35,
      (__int64)&v34,
      (__int64)&v41,
      (__int64)&v40,
      (__int64)&v38,
      (__int64)&v39);
  }
  v38 = (char *)this + 56;
  v12 = *((_QWORD *)this + 7);
  v33 = *(_DWORD *)(v12 + 120);
  try
  {
    Rdp::Modern::Utils::CInflightRecorder::pushN(
      (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      (wchar_t *)L"HevcFrameProcessorStop: Id {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}",
      "Rdp::Avenc::Hevc::CHevcFrameProcessor::Stop",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcframeprocessor.cpp",
      0x98u);
    v13 = *((_QWORD *)this + 6);
    if ( v13 )
    {
      v14 = *(_QWORD *)(v13 + 224);
      *(_QWORD *)(v13 + 224) = 0;
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      v15 = *((_QWORD *)this + 6);
      *((_QWORD *)this + 6) = 0;
      if ( v15 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v15 + 24LL))(v15, 1);
    }
    v16 = std::_Locked_pointer<std::_Ref_count_base>::_Lock_and_load((char *)this + 40);
    v17 = (volatile signed __int32 *)v16;
    v39 = (volatile signed __int32 *)v16;
    v18 = (Rdp::Avenc::CFcWireEncoderWithBulkUncompressed *)*((_QWORD *)this + 4);
    v36[0] = v18;
    v36[1] = v16;
    if ( v16 )
      _InterlockedAdd((volatile signed __int32 *)(v16 + 8), 1u);
    if ( (_InterlockedExchange64((volatile __int64 *)this + 5, v16) & 3) == 2 )
      WakeByAddressAll((char *)this + 40);
    v35 = 0;
    std::atomic<std::shared_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>>>::store(
      (char *)this + 32,
      &v35);
    if ( v18 )
    {
      try
      {
        Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::AllocatePool(v18, 0x1000u, 0, 0);
        v23 = (__int64 *)v38;
        v20 = *(_DWORD *)(*(_QWORD *)v38 + 136LL);
        v21 = Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::EnsureBuffer(v18, 0xAu);
        wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(
          retaddr,
          343,
          "onecoreuap\\termsrv\\rdp_bin\\win\\common/protocol/RdpEgfx/RdpEgfx.h",
          2147942414LL,
          v21,
          "Unable to ensure RDPGFX_DELETE_SURFACE_PDU_SIZE");
        *v21 = 10;
        v21[1] = 10;
        *((_WORD *)v21 + 4) = v20;
        Rdp::Avenc::CFcWireEncoder::Flush(v18, v22);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0xB0,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcframeprocessor.cpp",
          v19);
        v5 = 1;
        v17 = v39;
        goto LABEL_24;
      }
    }
    else
    {
LABEL_24:
      v23 = (__int64 *)v38;
    }
    v24 = *v23;
    *v23 = 0;
    if ( v24 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v5 = 0;
    }
    v25 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v26 = GetCurrentThreadId();
      LOBYTE(v27) = v25;
      LOBYTE(v28) = v5;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v28,
        v27,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v31,
        v33,
        13,
        &WPP_bc0801f283643948a642b8834c5cca7a_Traceguids,
        v26);
    }
    if ( v17 )
    {
      if ( _InterlockedExchangeAdd(v17 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
        if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
      }
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xB8,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcframeprocessor.cpp",
                           v19);
  }
  return result;
}

```

## disassembly

```asm
0x18002d3a0  push    rbx
0x18002d3a2  push    rsi
0x18002d3a3  push    rdi
0x18002d3a4  push    r12
0x18002d3a6  push    r13
0x18002d3a8  push    r14
0x18002d3aa  push    r15
0x18002d3ac  sub     rsp, 0B0h
0x18002d3b3  mov     r13, rcx
0x18002d3b6  lea     rcx, WPP_GLOBAL_Control
0x18002d3bd  mov     rax, cs:WPP_GLOBAL_Control
0x18002d3c4  mov     r12d, 1
0x18002d3ca  cmp     rax, rcx
0x18002d3cd  jz      short loc_18002D3E3
0x18002d3cf  test    [rax+1Ch], r12b
0x18002d3d3  jz      short loc_18002D3E3
0x18002d3d5  cmp     byte ptr [rax+19h], 4
0x18002d3d9  jb      short loc_18002D3E3
0x18002d3db  mov     bl, r12b
0x18002d3de  xor     r15d, r15d
0x18002d3e1  jmp     short loc_18002D3E9
0x18002d3e3  xor     r15d, r15d
0x18002d3e6  mov     bl, r15b
0x18002d3e9  lea     rax, WPP_RECORDER_INITIALIZED
0x18002d3f0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002d3f7  setnz   dil
0x18002d3fb  test    bl, bl
0x18002d3fd  jnz     short loc_18002D404
0x18002d3ff  test    dil, dil
0x18002d402  jz      short loc_18002D43A
0x18002d404  call    cs:__imp_GetCurrentThreadId
0x18002d40a  mov     dword ptr [rsp+0E8h+var_A8], eax; char
0x18002d40e  lea     rsi, WPP_bc0801f283643948a642b8834c5cca7a_Traceguids
0x18002d415  mov     [rsp+0E8h+MessageGuid], rsi; MessageGuid
0x18002d41a  mov     [rsp+0E8h+var_B8], 0Ch; __int16
0x18002d421  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d428  mov     r9, [rcx+28h]; int
0x18002d42c  mov     r8b, dil; int
0x18002d42f  mov     dl, bl; int
0x18002d431  mov     rcx, [rcx+10h]; int
0x18002d435  call    WPP_RECORDER_AND_TRACE_SF_D
0x18002d43a  mov     eax, cs:dword_1800C1058
0x18002d440  cmp     eax, 4
0x18002d443  jbe     loc_18002D550
0x18002d449  mov     rcx, cs:qword_1800C1070
0x18002d450  mov     rax, cs:qword_1800C1068
0x18002d457  mov     rdx, 470000000000h
0x18002d461  test    rdx, rax
0x18002d464  jz      loc_18002D550
0x18002d46a  mov     rax, rcx
0x18002d46d  and     rax, rdx
0x18002d470  cmp     rax, rcx
0x18002d473  jnz     loc_18002D550
0x18002d479  mov     rcx, [r13+38h]
0x18002d47d  lea     rax, [rcx+78h]
0x18002d481  mov     [rsp+0E8h+arg_8], rax
0x18002d489  mov     rax, [rcx+70h]
0x18002d48d  mov     ecx, [rax+0A0h]
0x18002d493  mov     dword ptr [rsp+0E8h+arg_0], ecx
0x18002d49a  lea     rax, aStopHevcFrameP; "Stop Hevc frame processor"
0x18002d4a1  mov     [rsp+0E8h+arg_10], rax
0x18002d4a9  lea     rax, xmmword_1800C21A0
0x18002d4b0  mov     [rsp+0E8h+arg_18], rax
0x18002d4b8  lea     rax, aRdpavenc; "RdpAvenc"
0x18002d4bf  mov     [rsp+0E8h+var_68], rax
0x18002d4c7  mov     qword ptr [rsp+0E8h+var_60], 1000000h
0x18002d4d3  lea     rax, aCheckpoint; "Checkpoint"
0x18002d4da  mov     [rsp+0E8h+var_50], rax
0x18002d4e2  lea     rax, [rsp+0E8h+arg_8]
0x18002d4ea  mov     [rsp+0E8h+var_98], rax
0x18002d4ef  lea     rax, [rsp+0E8h+arg_0]
0x18002d4f7  mov     [rsp+0E8h+var_A0], rax
0x18002d4fc  lea     rax, [rsp+0E8h+arg_10]
0x18002d504  mov     qword ptr [rsp+0E8h+var_A8], rax
0x18002d509  lea     rax, [rsp+0E8h+arg_18]
0x18002d511  mov     [rsp+0E8h+MessageGuid], rax
0x18002d516  lea     rax, [rsp+0E8h+var_68]
0x18002d51e  mov     qword ptr [rsp+0E8h+var_B8], rax
0x18002d523  lea     rax, [rsp+0E8h+var_60]
0x18002d52b  mov     [rsp+0E8h+var_C0], rax
0x18002d530  lea     rax, [rsp+0E8h+var_50]
0x18002d538  mov     qword ptr [rsp+0E8h+var_C8], rax
0x18002d53d  lea     rdx, word_1800AE7A2
0x18002d544  lea     rcx, dword_1800C1058
0x18002d54b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x18002d550  lea     rax, [r13+38h]
0x18002d554  mov     [rsp+0E8h+arg_0], rax
0x18002d55c  mov     r14, [rax]
0x18002d55f  movzx   eax, byte ptr [r14+87h]
0x18002d567  movzx   ecx, byte ptr [r14+86h]
0x18002d56f  movzx   edx, byte ptr [r14+85h]
0x18002d577  movzx   r8d, byte ptr [r14+84h]
0x18002d57f  movzx   r9d, byte ptr [r14+83h]
0x18002d587  movzx   r10d, byte ptr [r14+82h]
0x18002d58f  movzx   r11d, byte ptr [r14+81h]
0x18002d597  movzx   ebx, byte ptr [r14+80h]
0x18002d59f  movzx   edi, word ptr [r14+7Eh]
0x18002d5a4  movzx   esi, word ptr [r14+7Ch]
0x18002d5a9  mov     [rsp+0E8h+var_70], eax
0x18002d5ad  mov     [rsp+0E8h+var_78], ecx
0x18002d5b1  mov     [rsp+0E8h+var_80], edx
0x18002d5b5  mov     [rsp+0E8h+var_88], r8d
0x18002d5ba  mov     [rsp+0E8h+var_90], r9d
0x18002d5bf  mov     dword ptr [rsp+0E8h+var_98], r10d
0x18002d5c4  mov     dword ptr [rsp+0E8h+var_A0], r11d
0x18002d5c9  mov     dword ptr [rsp+0E8h+var_A8], ebx
0x18002d5cd  mov     dword ptr [rsp+0E8h+MessageGuid], edi
0x18002d5d1  mov     dword ptr [rsp+0E8h+var_B8], esi
0x18002d5d5  mov     eax, [r14+78h]
0x18002d5d9  mov     dword ptr [rsp+0E8h+var_C0], eax
0x18002d5dd  mov     [rsp+0E8h+var_C8], 98h; unsigned int
0x18002d5e5  lea     r9, aOnecoreuapTerm_57; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18002d5ec  lea     r8, aRdpAvencHevcCh_5; "Rdp::Avenc::Hevc::CHevcFrameProcessor::"...
0x18002d5f3  lea     rdx, aHevcframeproce_0; "HevcFrameProcessorStop: Id {%08lX-%04hX"...
0x18002d5fa  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18002d601  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18002d606  mov     rax, [r13+30h]
0x18002d60a  test    rax, rax
0x18002d60d  jz      short loc_18002D64B
0x18002d60f  mov     rcx, [rax+0E0h]
0x18002d616  mov     [rax+0E0h], r15
0x18002d61d  test    rcx, rcx
0x18002d620  jz      short loc_18002D62F
0x18002d622  mov     rax, [rcx]
0x18002d625  mov     rax, [rax+10h]
0x18002d629  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d62e  nop
0x18002d62f  mov     rcx, [r13+30h]
0x18002d633  mov     [r13+30h], r15
0x18002d637  test    rcx, rcx
0x18002d63a  jz      short loc_18002D64B
0x18002d63c  mov     rax, [rcx]
0x18002d63f  mov     edx, r12d
0x18002d642  mov     rax, [rax+18h]
0x18002d646  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d64b  lea     rdi, [r13+28h]
0x18002d64f  mov     rcx, rdi; Address
0x18002d652  call    ?_Lock_and_load@?$_Locked_pointer@V_Ref_count_base@std@@@std@@QEAAPEAV_Ref_count_base@2@XZ; std::_Locked_pointer<std::_Ref_count_base>::_Lock_and_load(void)
0x18002d657  mov     rbx, rax
0x18002d65a  mov     [rsp+0E8h+arg_8], rax
0x18002d662  mov     rsi, [r13+20h]
0x18002d666  mov     [rsp+0E8h+var_50], rsi
0x18002d66e  mov     [rsp+0E8h+var_48], rax
0x18002d676  test    rax, rax
0x18002d679  jz      short loc_18002D680
0x18002d67b  lock add [rax+8], r12d
0x18002d680  mov     rdx, rax
0x18002d683  xchg    rdx, [rdi]
0x18002d686  and     dl, 3
0x18002d689  cmp     dl, 2
0x18002d68c  jnz     short loc_18002D698
0x18002d68e  mov     rcx, rdi; Address
0x18002d691  call    cs:__imp_WakeByAddressAll
0x18002d697  nop
0x18002d698  xorps   xmm0, xmm0
0x18002d69b  movdqu  [rsp+0E8h+var_60], xmm0
0x18002d6a4  lea     rdx, [rsp+0E8h+var_60]
0x18002d6ac  lea     rcx, [r13+20h]
0x18002d6b0  call    ?store@?$atomic@V?$shared_ptr@V?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@@std@@@std@@QEAAXV?$shared_ptr@V?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@@2@W4memory_order@2@@Z; std::atomic<std::shared_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>>>::store(std::shared_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>>,std::memory_order)
0x18002d6b5  test    rsi, rsi
0x18002d6b8  jz      loc_18002D74E
0x18002d6be  xor     r9d, r9d; unsigned __int64
0x18002d6c1  xor     r8d, r8d; unsigned int
0x18002d6c4  mov     edx, 1000h; unsigned __int64
0x18002d6c9  mov     rcx, rsi; this
0x18002d6cc  call    ?AllocatePool@CFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@QEAAX_KI0@Z; Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::AllocatePool(unsigned __int64,uint,unsigned __int64)
0x18002d6d1  mov     r14, [rsp+0E8h+arg_0]
0x18002d6d9  mov     rax, [r14]
0x18002d6dc  mov     r13d, [rax+88h]
0x18002d6e3  mov     edx, 0Ah; unsigned __int64
0x18002d6e8  mov     rcx, rsi; this
0x18002d6eb  call    ?EnsureBuffer@CFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@QEAAPEAX_K@Z; Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::EnsureBuffer(unsigned __int64)
0x18002d6f0  mov     rdi, rax
0x18002d6f3  mov     rcx, [rsp+0E8h]
0x18002d6fb  lea     rax, aUnableToEnsure_20; "Unable to ensure RDPGFX_DELETE_SURFACE_"...
0x18002d702  mov     [rsp+0E8h+var_C0], rax
0x18002d707  mov     qword ptr [rsp+0E8h+var_C8], rdi
0x18002d70c  mov     r9d, 8007000Eh
0x18002d712  lea     r8, aOnecoreuapTerm_14; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x18002d719  mov     edx, 157h
0x18002d71e  call    ??$Throw_HrIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBDJ01ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(void *,uint,char const *,long,void *,char const *,...)
0x18002d723  mov     eax, 0Ah
0x18002d728  mov     [rdi], eax
0x18002d72a  mov     [rdi+4], eax
0x18002d72d  mov     [rdi+8], r13w
0x18002d732  mov     rcx, rsi; this
0x18002d735  call    ?Flush@CFcWireEncoder@Avenc@Rdp@@QEAAXI@Z; Rdp::Avenc::CFcWireEncoder::Flush(uint)
0x18002d73a  nop
0x18002d73b  jmp     short loc_18002D756
0x18002d73d  mov     r12d, 1
0x18002d743  xor     r15d, r15d
0x18002d746  mov     rbx, [rsp+0E8h+arg_8]
0x18002d74e  mov     r14, [rsp+0E8h+arg_0]
0x18002d756  lea     rdi, WPP_GLOBAL_Control
0x18002d75d  lea     rsi, WPP_RECORDER_INITIALIZED
0x18002d764  lea     r13, WPP_bc0801f283643948a642b8834c5cca7a_Traceguids
0x18002d76b  mov     rcx, [r14]
0x18002d76e  mov     [r14], r15
0x18002d771  test    rcx, rcx
0x18002d774  jz      short loc_18002D783
0x18002d776  mov     rax, [rcx]
0x18002d779  mov     rax, [rax+10h]
0x18002d77d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d782  nop
0x18002d783  mov     rax, cs:WPP_GLOBAL_Control
0x18002d78a  cmp     rax, rdi
0x18002d78d  jz      short loc_18002D79B
0x18002d78f  test    [rax+1Ch], r12b
0x18002d793  jz      short loc_18002D79B
0x18002d795  cmp     byte ptr [rax+19h], 4
0x18002d799  jnb     short loc_18002D79E
0x18002d79b  mov     r12b, r15b
0x18002d79e  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x18002d7a5  setnz   dil
0x18002d7a9  test    r12b, r12b
0x18002d7ac  jnz     short loc_18002D7B3
0x18002d7ae  test    dil, dil
0x18002d7b1  jz      short loc_18002D7E4
0x18002d7b3  call    cs:__imp_GetCurrentThreadId
0x18002d7b9  mov     dword ptr [rsp+0E8h+var_A8], eax; char
0x18002d7bd  mov     [rsp+0E8h+MessageGuid], r13; MessageGuid
0x18002d7c2  mov     [rsp+0E8h+var_B8], 0Dh; __int16
0x18002d7c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d7d0  mov     r9, [rcx+28h]; int
0x18002d7d4  mov     r8b, dil; int
0x18002d7d7  mov     dl, r12b; int
0x18002d7da  mov     rcx, [rcx+10h]; int
0x18002d7de  call    WPP_RECORDER_AND_TRACE_SF_D
0x18002d7e3  nop
0x18002d7e4  test    rbx, rbx
0x18002d7e7  jz      short loc_18002D81F
0x18002d7e9  or      edi, 0FFFFFFFFh
0x18002d7ec  mov     eax, edi
0x18002d7ee  lock xadd [rbx+8], eax
0x18002d7f3  add     eax, edi
0x18002d7f5  jnz     short loc_18002D81F
0x18002d7f7  mov     rax, [rbx]
0x18002d7fa  mov     rcx, rbx
0x18002d7fd  mov     rax, [rax]
0x18002d800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d805  mov     eax, edi
0x18002d807  lock xadd [rbx+0Ch], eax
0x18002d80c  add     eax, edi
0x18002d80e  jnz     short loc_18002D81F
0x18002d810  mov     rax, [rbx]
0x18002d813  mov     rcx, rbx
0x18002d816  mov     rax, [rax+8]
0x18002d81a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d81f  xor     eax, eax
0x18002d821  jmp     short loc_18002D82A
0x18002d823  mov     eax, dword ptr [rsp+0E8h+arg_0]
0x18002d82a  add     rsp, 0B0h
0x18002d831  pop     r15
0x18002d833  pop     r14
0x18002d835  pop     r13
0x18002d837  pop     r12
0x18002d839  pop     rdi
0x18002d83a  pop     rsi
0x18002d83b  pop     rbx
0x18002d83c  retn
```
