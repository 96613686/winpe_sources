# Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::ICpuFrameProcessor,Rdp::Avenc::ICpuFrameAsyncProcessor>::Stop(void)

- ea: `0x18004c050`
- end: `0x18004c5e6`
- name: `?Stop@?$CIc3FrameProcessor@UICpuFrameProcessor@Avenc@Rdp@@UICpuFrameAsyncProcessor@23@@Ic3@Avenc@Rdp@@UEAAJXZ`
- size: `1430`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180044ea0`

## callees

- `0x18000406c`
- `0x1800050dc`
- `0x1800103c0`
- `0x180010bc8`
- `0x180011490`
- `0x1800153f8`
- `0x180015480`
- `0x1800203d4`
- `0x180026f90`
- `0x180042084`
- `0x18004c050`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004c125`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004c51d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004c125`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004c51d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004c0b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004c55f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004c0b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004c55f`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18004c132`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18004c132`

## string_xrefs

- `0x18004c230`: `DirectStreamMedia_Service`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::ICpuFrameProcessor,Rdp::Avenc::ICpuFrameAsyncProcessor>::Stop(
        __int64 a1)
{
  char v2; // r12
  bool v3; // bl
  bool v4; // di
  char CurrentThreadId; // al
  int v6; // r8d
  int v7; // edx
  int v8; // eax
  bool v9; // zf
  int v10; // r8d
  int v11; // r9d
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r14
  int v17; // r8d
  int v18; // r9d
  __int64 v19; // rdx
  unsigned int v20; // eax
  const char *v21; // r9
  __int64 v22; // rcx
  bool v23; // bl
  char v24; // al
  int v25; // r8d
  int v26; // edx
  __int64 result; // rax
  int v28; // [rsp+20h] [rbp-C8h]
  int v29; // [rsp+20h] [rbp-C8h]
  char *v30; // [rsp+28h] [rbp-C0h]
  int v31; // [rsp+28h] [rbp-C0h]
  __int16 v32[4]; // [rsp+30h] [rbp-B8h]
  LPCGUID MessageGuid; // [rsp+38h] [rbp-B0h]
  char v34[8]; // [rsp+40h] [rbp-A8h]
  __int64 v35; // [rsp+48h] [rbp-A0h]
  __int64 v36; // [rsp+50h] [rbp-98h]
  __int64 v37; // [rsp+58h] [rbp-90h]
  __int64 v38; // [rsp+60h] [rbp-88h]
  int *v39; // [rsp+80h] [rbp-68h] BYREF
  const char *v40; // [rsp+88h] [rbp-60h] BYREF
  const char *v41; // [rsp+90h] [rbp-58h] BYREF
  __int64 v42; // [rsp+98h] [rbp-50h] BYREF
  _QWORD v43[9]; // [rsp+A0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]
  int v45; // [rsp+F0h] [rbp+8h] BYREF
  int v46; // [rsp+F8h] [rbp+10h] BYREF
  __int64 v47; // [rsp+100h] [rbp+18h] BYREF
  const char *v48; // [rsp+108h] [rbp+20h] BYREF

  v2 = 1;
  v3 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v4 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v6) = v4;
    LOBYTE(v7) = v3;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      v6,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v28,
      (int)v30,
      12,
      &WPP_82575e15b34e32cfad750d208edc4dfe_Traceguids,
      CurrentThreadId);
  }
  v8 = mtx_do_lock(a1 + 176);
  try
  {
    if ( v8 )
      std::_Throw_Cpp_error(5);
    if ( *(_DWORD *)(a1 + 252) == 0x7FFFFFFF )
    {
      *(_DWORD *)(a1 + 252) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    *(_BYTE *)(a1 + 352) = 1;
    v9 = (*(_DWORD *)(a1 + 252))-- == 1;
    if ( v9 )
    {
      *(_DWORD *)(a1 + 248) = -1;
      ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 192));
    }
    WakeAllConditionVariable((PCONDITION_VARIABLE)(a1 + 264));
    if ( *(_DWORD *)(a1 + 336) )
      std::thread::join((std::thread *)(a1 + 328));
    v12 = *(_QWORD *)(a1 + 160);
    *(_QWORD *)(a1 + 160) = 0;
    if ( v12 )
    {
      v13 = v12 + 8 + *(int *)(*(_QWORD *)(v12 + 8) + 4LL);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    v14 = *(_QWORD *)(a1 + 168);
    *(_QWORD *)(a1 + 168) = 0;
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
    if ( (unsigned int)dword_1800C1058 > 4
      && (qword_1800C1068 & 0x470000000000LL) != 0
      && (qword_1800C1070 & 0x470000000000LL) == qword_1800C1070 )
    {
      v15 = *(_QWORD *)(a1 + 96);
      v47 = v15 + 112;
      v45 = *(_DWORD *)(*(_QWORD *)(v15 + 104) + 136LL);
      v46 = *(_DWORD *)(v15 + 128);
      v48 = "Stop Ic3 frame processor";
      v39 = &xmmword_1800C21A0;
      v40 = "DirectStreamMedia_Service";
      v41 = "RdpAvenc";
      v42 = 0x1000000;
      v43[0] = "Checkpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)word_1800B0D7A,
        v10,
        v11,
        (__int64)v43,
        (__int64)&v42,
        (__int64)&v41,
        (__int64)&v40,
        (__int64)&v39,
        (__int64)&v48,
        (__int64)&v46,
        (__int64)&v45,
        (__int64)&v47);
    }
    v16 = *(_QWORD *)(a1 + 96);
    LODWORD(v38) = *(unsigned __int8 *)(v16 + 124);
    LODWORD(v37) = *(unsigned __int8 *)(v16 + 123);
    LODWORD(v36) = *(unsigned __int8 *)(v16 + 122);
    LODWORD(v35) = *(unsigned __int8 *)(v16 + 121);
    *(_DWORD *)v34 = *(unsigned __int8 *)(v16 + 120);
    LODWORD(MessageGuid) = *(unsigned __int16 *)(v16 + 118);
    *(_DWORD *)v32 = *(unsigned __int16 *)(v16 + 116);
    LODWORD(v30) = *(_DWORD *)(v16 + 112);
    Rdp::Modern::Utils::CInflightRecorder::pushN(
      (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      (wchar_t *)L"Ic3FrameProcessorStop: Id {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}",
      "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::ICpuFrameProcessor,struct Rdp::Avenc::ICpuFrameAsyncProcessor>::Stop",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
      0x120u,
      v30,
      *(_QWORD *)v32,
      MessageGuid,
      *(_QWORD *)v34,
      v35,
      v36,
      v37,
      v38,
      *(unsigned __int8 *)(v16 + 125),
      *(unsigned __int8 *)(v16 + 126),
      *(unsigned __int8 *)(v16 + 127));
    if ( (unsigned int)dword_1800C1058 > 5 )
    {
      v19 = *(_QWORD *)(a1 + 96);
      v48 = (const char *)(v19 + 112);
      v45 = *(_DWORD *)(*(_QWORD *)(v19 + 104) + 136LL);
      v46 = *(_DWORD *)(v19 + 128);
      v43[0] = "StopFrameProcessor";
      v42 = (__int64)"Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::ICpuFrameProcessor,struct Rdp::Avenc::ICpuFr"
                     "ameAsyncProcessor>::Stop";
      LODWORD(v47) = 296;
      v41 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)word_1800B0CBA,
        v17,
        v18,
        (__int64)&v41,
        (__int64)&v47,
        (__int64)&v42,
        (__int64)v43,
        (__int64)&v46,
        (__int64)&v45,
        (__int64)&v48);
    }
    wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(
      retaddr,
      298,
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
      2147549183LL);
    v20 = Rdp::Avenc::Ic3::CDsGfxChannel::SendStopStreamPdu(
            *(Rdp::Avenc::Ic3::CDsGfxChannel **)(a1 + 144),
            (const struct _GUID *)(*(_QWORD *)(a1 + 96) + 112LL),
            *(_DWORD *)(*(_QWORD *)(a1 + 96) + 128LL));
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      (void *)0x12D,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
      (const char *)v20,
      (int)"Unable to send stop stream pdu.",
      "Direct streaming GFX channel is not set.");
    if ( (unsigned int)mtx_do_lock(a1 + 16) )
      std::_Throw_Cpp_error(5);
    if ( *(_DWORD *)(a1 + 92) == 0x7FFFFFFF )
    {
      *(_DWORD *)(a1 + 92) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    v22 = *(_QWORD *)(a1 + 96);
    *(_QWORD *)(a1 + 96) = 0;
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v9 = (*(_DWORD *)(a1 + 92))-- == 1;
    if ( v9 )
    {
      *(_DWORD *)(a1 + 88) = -1;
      ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 32));
    }
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v2 = 0;
    }
    v23 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v24 = GetCurrentThreadId();
      LOBYTE(v25) = v23;
      LOBYTE(v26) = v2;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v26,
        v25,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v29,
        v31,
        13,
        &WPP_82575e15b34e32cfad750d208edc4dfe_Traceguids,
        v24);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x136,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
                           v21);
  }
  return result;
}

```

## disassembly

```asm
0x18004c050  push    rbx
0x18004c052  push    rsi
0x18004c053  push    rdi
0x18004c054  push    r12
0x18004c056  push    r13
0x18004c058  push    r14
0x18004c05a  push    r15
0x18004c05c  sub     rsp, 0B0h
0x18004c063  mov     r15, rcx
0x18004c066  lea     rcx, WPP_GLOBAL_Control
0x18004c06d  mov     rax, cs:WPP_GLOBAL_Control
0x18004c074  mov     r12b, 1
0x18004c077  cmp     rax, rcx
0x18004c07a  jz      short loc_18004C08D
0x18004c07c  test    [rax+1Ch], r12b
0x18004c080  jz      short loc_18004C08D
0x18004c082  cmp     byte ptr [rax+19h], 4
0x18004c086  jb      short loc_18004C08D
0x18004c088  mov     bl, r12b
0x18004c08b  jmp     short loc_18004C08F
0x18004c08d  xor     bl, bl
0x18004c08f  lea     rax, WPP_RECORDER_INITIALIZED
0x18004c096  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18004c09d  setnz   dil
0x18004c0a1  test    bl, bl
0x18004c0a3  jnz     short loc_18004C0B3
0x18004c0a5  test    dil, dil
0x18004c0a8  jnz     short loc_18004C0B3
0x18004c0aa  lea     r13, WPP_82575e15b34e32cfad750d208edc4dfe_Traceguids
0x18004c0b1  jmp     short loc_18004C0E9
0x18004c0b3  call    cs:__imp_GetCurrentThreadId
0x18004c0b9  mov     dword ptr [rsp+0E8h+var_A8], eax; char
0x18004c0bd  lea     r13, WPP_82575e15b34e32cfad750d208edc4dfe_Traceguids
0x18004c0c4  mov     [rsp+0E8h+MessageGuid], r13; MessageGuid
0x18004c0c9  mov     [rsp+0E8h+var_B8], 0Ch; __int16
0x18004c0d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c0d7  mov     r9, [rcx+28h]; int
0x18004c0db  mov     r8b, dil; int
0x18004c0de  mov     dl, bl; int
0x18004c0e0  mov     rcx, [rcx+10h]; int
0x18004c0e4  call    WPP_RECORDER_AND_TRACE_SF_D
0x18004c0e9  lea     rbx, [r15+0B0h]
0x18004c0f0  mov     rcx, rbx
0x18004c0f3  call    mtx_do_lock
0x18004c0f8  test    eax, eax
0x18004c0fa  jnz     loc_18004C5AD
0x18004c100  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x18004c107  jz      loc_18004C5B7
0x18004c10d  mov     [r15+160h], r12b
0x18004c114  sub     dword ptr [rbx+4Ch], 1
0x18004c118  jnz     short loc_18004C12B
0x18004c11a  mov     dword ptr [rbx+48h], 0FFFFFFFFh
0x18004c121  lea     rcx, [rbx+10h]; SRWLock
0x18004c125  call    cs:__imp_ReleaseSRWLockExclusive
0x18004c12b  lea     rcx, [r15+108h]; ConditionVariable
0x18004c132  call    cs:__imp_WakeAllConditionVariable
0x18004c138  cmp     dword ptr [r15+150h], 0
0x18004c140  jz      short loc_18004C14E
0x18004c142  lea     rcx, [r15+148h]; this
0x18004c149  call    ?join@thread@std@@QEAAXXZ; std::thread::join(void)
0x18004c14e  mov     rdx, [r15+0A0h]
0x18004c155  mov     qword ptr [r15+0A0h], 0
0x18004c160  test    rdx, rdx
0x18004c163  jz      short loc_18004C181
0x18004c165  mov     rax, [rdx+8]
0x18004c169  movsxd  rcx, dword ptr [rax+4]
0x18004c16d  add     rdx, 8
0x18004c171  add     rcx, rdx
0x18004c174  mov     rax, [rcx]
0x18004c177  mov     rax, [rax+10h]
0x18004c17b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c180  nop
0x18004c181  mov     rcx, [r15+0A8h]
0x18004c188  mov     qword ptr [r15+0A8h], 0
0x18004c193  test    rcx, rcx
0x18004c196  jz      short loc_18004C1A5
0x18004c198  mov     rax, [rcx]
0x18004c19b  mov     rax, [rax+8]
0x18004c19f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c1a4  nop
0x18004c1a5  mov     eax, cs:dword_1800C1058
0x18004c1ab  cmp     eax, 4
0x18004c1ae  jbe     loc_18004C2F1
0x18004c1b4  mov     rcx, cs:qword_1800C1070
0x18004c1bb  mov     rax, cs:qword_1800C1068
0x18004c1c2  mov     rdx, 470000000000h
0x18004c1cc  test    rdx, rax
0x18004c1cf  jz      loc_18004C2F1
0x18004c1d5  mov     rax, rcx
0x18004c1d8  and     rax, rdx
0x18004c1db  cmp     rax, rcx
0x18004c1de  jnz     loc_18004C2F1
0x18004c1e4  mov     rdx, [r15+60h]
0x18004c1e8  lea     rax, [rdx+70h]
0x18004c1ec  mov     [rsp+0E8h+arg_10], rax
0x18004c1f4  mov     rax, [rdx+68h]
0x18004c1f8  mov     ecx, [rax+88h]
0x18004c1fe  mov     [rsp+0E8h+arg_0], ecx
0x18004c205  mov     eax, [rdx+80h]
0x18004c20b  mov     [rsp+0E8h+arg_8], eax
0x18004c212  lea     rax, aStopIc3FramePr; "Stop Ic3 frame processor"
0x18004c219  mov     [rsp+0E8h+arg_18], rax
0x18004c221  lea     rax, xmmword_1800C21A0
0x18004c228  mov     [rsp+0E8h+var_68], rax
0x18004c230  lea     rax, aDirectstreamme; "DirectStreamMedia_Service"
0x18004c237  mov     [rsp+0E8h+var_60], rax
0x18004c23f  lea     rax, aRdpavenc; "RdpAvenc"
0x18004c246  mov     [rsp+0E8h+var_58], rax
0x18004c24e  mov     [rsp+0E8h+var_50], 1000000h
0x18004c25a  lea     rax, aCheckpoint; "Checkpoint"
0x18004c261  mov     [rsp+0E8h+var_48], rax
0x18004c269  lea     rax, [rsp+0E8h+arg_10]
0x18004c271  mov     [rsp+0E8h+var_88], rax
0x18004c276  lea     rax, [rsp+0E8h+arg_0]
0x18004c27e  mov     [rsp+0E8h+var_90], rax
0x18004c283  lea     rax, [rsp+0E8h+arg_8]
0x18004c28b  mov     [rsp+0E8h+var_98], rax
0x18004c290  lea     rax, [rsp+0E8h+arg_18]
0x18004c298  mov     [rsp+0E8h+var_A0], rax
0x18004c29d  lea     rax, [rsp+0E8h+var_68]
0x18004c2a5  mov     qword ptr [rsp+0E8h+var_A8], rax
0x18004c2aa  lea     rax, [rsp+0E8h+var_60]
0x18004c2b2  mov     [rsp+0E8h+MessageGuid], rax
0x18004c2b7  lea     rax, [rsp+0E8h+var_58]
0x18004c2bf  mov     qword ptr [rsp+0E8h+var_B8], rax
0x18004c2c4  lea     rax, [rsp+0E8h+var_50]
0x18004c2cc  mov     [rsp+0E8h+var_C0], rax
0x18004c2d1  lea     rax, [rsp+0E8h+var_48]
0x18004c2d9  mov     qword ptr [rsp+0E8h+var_C8], rax
0x18004c2de  lea     rdx, word_1800B0D7A
0x18004c2e5  lea     rcx, dword_1800C1058
0x18004c2ec  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U4@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@33AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@65@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x18004c2f1  mov     r14, [r15+60h]
0x18004c2f5  movzx   eax, byte ptr [r14+7Fh]
0x18004c2fa  movzx   ecx, byte ptr [r14+7Eh]
0x18004c2ff  movzx   edx, byte ptr [r14+7Dh]
0x18004c304  movzx   r8d, byte ptr [r14+7Ch]
0x18004c309  movzx   r9d, byte ptr [r14+7Bh]
0x18004c30e  movzx   r10d, byte ptr [r14+7Ah]
0x18004c313  movzx   r11d, byte ptr [r14+79h]
0x18004c318  movzx   ebx, byte ptr [r14+78h]
0x18004c31d  movzx   edi, word ptr [r14+76h]
0x18004c322  movzx   esi, word ptr [r14+74h]
0x18004c327  mov     [rsp+0E8h+var_70], eax
0x18004c32b  mov     [rsp+0E8h+var_78], ecx
0x18004c32f  mov     [rsp+0E8h+var_80], edx
0x18004c333  mov     dword ptr [rsp+0E8h+var_88], r8d
0x18004c338  mov     dword ptr [rsp+0E8h+var_90], r9d
0x18004c33d  mov     dword ptr [rsp+0E8h+var_98], r10d
0x18004c342  mov     dword ptr [rsp+0E8h+var_A0], r11d
0x18004c347  mov     dword ptr [rsp+0E8h+var_A8], ebx
0x18004c34b  mov     dword ptr [rsp+0E8h+MessageGuid], edi
0x18004c34f  mov     dword ptr [rsp+0E8h+var_B8], esi
0x18004c353  mov     eax, [r14+70h]
0x18004c357  mov     dword ptr [rsp+0E8h+var_C0], eax
0x18004c35b  mov     [rsp+0E8h+var_C8], 120h; unsigned int
0x18004c363  lea     rdi, aOnecoreuapTerm_23; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18004c36a  mov     r9, rdi; char *
0x18004c36d  lea     rbx, aRdpAvencIc3Cic_0; "Rdp::Avenc::Ic3::CIc3FrameProcessor<str"...
0x18004c374  mov     r8, rbx; char *
0x18004c377  lea     rdx, aIc3frameproces_0; "Ic3FrameProcessorStop: Id {%08lX-%04hX-"...
0x18004c37e  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18004c385  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18004c38a  mov     eax, cs:dword_1800C1058
0x18004c390  cmp     eax, 5
0x18004c393  jbe     loc_18004C45F
0x18004c399  mov     rdx, [r15+60h]
0x18004c39d  lea     rax, [rdx+70h]
0x18004c3a1  mov     [rsp+0E8h+arg_18], rax
0x18004c3a9  mov     rax, [rdx+68h]
0x18004c3ad  mov     ecx, [rax+88h]
0x18004c3b3  mov     [rsp+0E8h+arg_0], ecx
0x18004c3ba  mov     eax, [rdx+80h]
0x18004c3c0  mov     [rsp+0E8h+arg_8], eax
0x18004c3c7  lea     rax, aStopframeproce; "StopFrameProcessor"
0x18004c3ce  mov     [rsp+0E8h+var_48], rax
0x18004c3d6  mov     [rsp+0E8h+var_50], rbx
0x18004c3de  mov     dword ptr [rsp+0E8h+arg_10], 128h
0x18004c3e9  mov     [rsp+0E8h+var_58], rdi
0x18004c3f1  lea     rax, [rsp+0E8h+arg_18]
0x18004c3f9  mov     [rsp+0E8h+var_98], rax
0x18004c3fe  lea     rax, [rsp+0E8h+arg_0]
0x18004c406  mov     [rsp+0E8h+var_A0], rax
0x18004c40b  lea     rax, [rsp+0E8h+arg_8]
0x18004c413  mov     qword ptr [rsp+0E8h+var_A8], rax
0x18004c418  lea     rax, [rsp+0E8h+var_48]
0x18004c420  mov     [rsp+0E8h+MessageGuid], rax
0x18004c425  lea     rax, [rsp+0E8h+var_50]
0x18004c42d  mov     qword ptr [rsp+0E8h+var_B8], rax
0x18004c432  lea     rax, [rsp+0E8h+arg_10]
0x18004c43a  mov     [rsp+0E8h+var_C0], rax
0x18004c43f  lea     rax, [rsp+0E8h+var_58]
0x18004c447  mov     qword ptr [rsp+0E8h+var_C8], rax
0x18004c44c  lea     rdx, word_1800B0CBA
0x18004c453  lea     rcx, dword_1800C1058
0x18004c45a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x18004c45f  lea     rbx, [r15+90h]
0x18004c466  mov     rcx, [rsp+0E8h]
0x18004c46e  lea     rax, aDirectStreamin; "Direct streaming GFX channel is not set"...
0x18004c475  mov     [rsp+0E8h+var_C0], rax; int
0x18004c47a  mov     qword ptr [rsp+0E8h+var_C8], rbx
0x18004c47f  mov     r9d, 8000FFFFh
0x18004c485  mov     r8, rdi
0x18004c488  mov     edx, 12Ah
0x18004c48d  call    ??$Throw_HrIfNullMsg@V?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@wil@@$0A@@in1diag3@details@wil@@YAXPEAXIPEBDJAEBV?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@2@1ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(void *,uint,char const *,long,wil::com_ptr_t<IPropertyStore,wil::err_exception_policy> const &,char const *,...)
0x18004c492  mov     r8, [r15+60h]
0x18004c496  lea     rdx, [r8+70h]; struct _GUID *
0x18004c49a  mov     r8d, [r8+80h]; unsigned int
0x18004c4a1  mov     rcx, [rbx]; this
0x18004c4a4  call    ?SendStopStreamPdu@CDsGfxChannel@Ic3@Avenc@Rdp@@QEAAJAEBU_GUID@@I@Z; Rdp::Avenc::Ic3::CDsGfxChannel::SendStopStreamPdu(_GUID const &,uint)
0x18004c4a9  mov     rcx, [rsp+0E8h]; this
0x18004c4b1  lea     rdx, aUnableToSendSt_0; "Unable to send stop stream pdu."
0x18004c4b8  mov     qword ptr [rsp+0E8h+var_C8], rdx; int
0x18004c4bd  mov     r9d, eax; char *
0x18004c4c0  mov     r8, rdi; unsigned int
0x18004c4c3  mov     edx, 12Dh; void *
0x18004c4c8  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18004c4cd  lea     rcx, [r15+10h]
0x18004c4d1  call    mtx_do_lock
0x18004c4d6  test    eax, eax
0x18004c4d8  jnz     loc_18004C5C8
0x18004c4de  cmp     dword ptr [r15+5Ch], 7FFFFFFFh
0x18004c4e6  jz      loc_18004C5D2
0x18004c4ec  mov     rcx, [r15+60h]
0x18004c4f0  mov     qword ptr [r15+60h], 0
0x18004c4f8  test    rcx, rcx
0x18004c4fb  jz      short loc_18004C50A
0x18004c4fd  mov     rax, [rcx]
0x18004c500  mov     rax, [rax+10h]
0x18004c504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c509  nop
0x18004c50a  sub     dword ptr [r15+5Ch], 1
0x18004c50f  jnz     short loc_18004C523
0x18004c511  mov     dword ptr [r15+58h], 0FFFFFFFFh
0x18004c519  lea     rcx, [r15+20h]; SRWLock
0x18004c51d  call    cs:__imp_ReleaseSRWLockExclusive
0x18004c523  mov     rax, cs:WPP_GLOBAL_Control
0x18004c52a  lea     rcx, WPP_GLOBAL_Control
0x18004c531  cmp     rax, rcx
0x18004c534  jz      short loc_18004C542
0x18004c536  test    [rax+1Ch], r12b
0x18004c53a  jz      short loc_18004C542
0x18004c53c  cmp     byte ptr [rax+19h], 4
0x18004c540  jnb     short loc_18004C545
0x18004c542  xor     r12b, r12b
0x18004c545  lea     rax, WPP_RECORDER_INITIALIZED
0x18004c54c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18004c553  setnz   bl
0x18004c556  test    r12b, r12b
0x18004c559  jnz     short loc_18004C55F
0x18004c55b  test    bl, bl
0x18004c55d  jz      short loc_18004C58F
0x18004c55f  call    cs:__imp_GetCurrentThreadId
0x18004c565  mov     dword ptr [rsp+0E8h+var_A8], eax; char
0x18004c569  mov     [rsp+0E8h+MessageGuid], r13; MessageGuid
0x18004c56e  mov     [rsp+0E8h+var_B8], 0Dh; __int16
0x18004c575  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c57c  mov     r9, [rcx+28h]; int
0x18004c580  mov     r8b, bl; int
0x18004c583  mov     dl, r12b; int
0x18004c586  mov     rcx, [rcx+10h]; int
0x18004c58a  call    WPP_RECORDER_AND_TRACE_SF_D
0x18004c58f  xor     eax, eax
0x18004c591  jmp     short loc_18004C59A
0x18004c593  mov     eax, [rsp+0E8h+arg_0]
0x18004c59a  add     rsp, 0B0h
0x18004c5a1  pop     r15
0x18004c5a3  pop     r14
0x18004c5a5  pop     r13
0x18004c5a7  pop     r12
0x18004c5a9  pop     rdi
0x18004c5aa  pop     rsi
0x18004c5ab  pop     rbx
0x18004c5ac  retn
0x18004c5ad  mov     ecx, 5; int
0x18004c5b2  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18004c5b7  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x18004c5be  mov     ecx, 6; int
0x18004c5c3  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18004c5c8  mov     ecx, 5; int
0x18004c5cd  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18004c5d2  mov     dword ptr [r15+5Ch], 7FFFFFFEh
0x18004c5da  mov     ecx, 6; int
0x18004c5df  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
