# Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::ICpuFrameProcessor,Rdp::Avenc::ICpuFrameAsyncProcessor>::Start(void)

- ea: `0x18004adb0`
- end: `0x18004b6eb`
- name: `?Start@?$CIc3FrameProcessor@UICpuFrameProcessor@Avenc@Rdp@@UICpuFrameAsyncProcessor@23@@Ic3@Avenc@Rdp@@UEAAJXZ`
- size: `2363`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180044a70`

## callees

- `0x18000406c`
- `0x1800047c0`
- `0x1800050dc`
- `0x1800065a4`
- `0x18000e848`
- `0x180010bc8`
- `0x180011490`
- `0x1800152c4`
- `0x180015480`
- `0x180041d0c`
- `0x18004adb0`
- `0x180089010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18004b51e`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18004b51e`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18004b4fb`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18004b4fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004ae0d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004b590`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004ae0d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004b590`

## string_xrefs

- `0x18004aec9`: `DirectStreamMedia_Service`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::ICpuFrameProcessor,Rdp::Avenc::ICpuFrameAsyncProcessor>::Start(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4)
{
  char v5; // si
  bool v6; // di
  bool v7; // r14
  char CurrentThreadId; // al
  int v9; // r8d
  int v10; // edx
  __int64 v11; // rdx
  int v12; // r8d
  int v13; // r9d
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rdi
  __int64 v17; // rdi
  void (__fastcall *v18)(__int64, __int64); // r12
  _QWORD *v19; // r14
  __int64 v20; // rcx
  int v21; // r8d
  int v22; // r9d
  __int64 v23; // rdx
  __int64 v24; // rax
  int v25; // r8d
  int v26; // r9d
  __int64 v27; // rdx
  __int64 v28; // rdx
  unsigned int started; // eax
  int v30; // r8d
  int v31; // r9d
  _QWORD *v32; // rax
  __int64 v33; // rdx
  __int64 v34; // rcx
  int v35; // ecx
  int v36; // eax
  bool v37; // r14
  char v38; // al
  int v39; // r8d
  int v40; // edx
  __int64 v41; // rdx
  const char *v42; // r9
  __int64 result; // rax
  int v44; // [rsp+20h] [rbp-B8h]
  int v45; // [rsp+20h] [rbp-B8h]
  int v46; // [rsp+28h] [rbp-B0h]
  struct tagRECT *v47; // [rsp+28h] [rbp-B0h]
  struct tagRECT *v48; // [rsp+28h] [rbp-B0h]
  const char *v49; // [rsp+70h] [rbp-68h] BYREF
  const char *v50; // [rsp+78h] [rbp-60h] BYREF
  const char *v51; // [rsp+80h] [rbp-58h] BYREF
  const char *v52; // [rsp+88h] [rbp-50h] BYREF
  int v53[4]; // [rsp+90h] [rbp-48h] BYREF
  _QWORD v54[7]; // [rsp+A0h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]
  _QWORD *v56; // [rsp+E8h] [rbp+10h] BYREF
  int v57; // [rsp+F0h] [rbp+18h] BYREF
  __int64 v58; // [rsp+F8h] [rbp+20h] BYREF

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
      v44,
      v46,
      10,
      &WPP_82575e15b34e32cfad750d208edc4dfe_Traceguids,
      CurrentThreadId);
  }
  if ( (unsigned int)dword_1800C1058 > 4
    && (qword_1800C1068 & 0x470000000000LL) != 0
    && (qword_1800C1070 & 0x470000000000LL) == qword_1800C1070 )
  {
    v11 = *(_QWORD *)(a1 + 96);
    v58 = v11 + 112;
    LODWORD(v56) = *(_DWORD *)(*(_QWORD *)(v11 + 104) + 136LL);
    v57 = *(_DWORD *)(v11 + 128);
    v49 = "Start Ic3 frame processor";
    v50 = (const char *)&xmmword_1800C21A0;
    v51 = "DirectStreamMedia_Service";
    v52 = "RdpAvenc";
    *(_QWORD *)v53 = 0x1000000;
    v54[0] = "Checkpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
      (unsigned int)&dword_1800C1058,
      (unsigned int)word_1800B0FE2,
      a3,
      a4,
      (__int64)v54,
      (__int64)v53,
      (__int64)&v52,
      (__int64)&v51,
      (__int64)&v50,
      (__int64)&v49,
      (__int64)&v57,
      (__int64)&v56,
      (__int64)&v58);
  }
  try
  {
    Rdp::Modern::Utils::CInflightRecorder::push0(
      (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      L"Ic3FrameProcessorStart",
      "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::ICpuFrameProcessor,struct Rdp::Avenc::ICpuFrameAsyncProcessor>::Start",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
      0xA0u);
    if ( (unsigned int)dword_1800C1058 > 5 )
    {
      v14 = *(_QWORD *)(a1 + 96);
      v54[0] = v14 + 112;
      LODWORD(v56) = *(_DWORD *)(*(_QWORD *)(v14 + 104) + 136LL);
      v57 = *(_DWORD *)(v14 + 128);
      *(_QWORD *)v53 = "StartFrameProcessor";
      v52 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::ICpuFrameProcessor,struct Rdp::Avenc::ICpuFrameAsyncP"
            "rocessor>::Start";
      LODWORD(v58) = 168;
      v51 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)word_1800B0EC2,
        v12,
        v13,
        (__int64)&v51,
        (__int64)&v58,
        (__int64)&v52,
        (__int64)v53,
        (__int64)&v57,
        (__int64)&v56,
        (__int64)v54);
    }
    v15 = *(_QWORD *)(*(_QWORD *)(a1 + 96) + 200LL);
    v16 = *(_QWORD *)(a1 + 144);
    *(_QWORD *)(a1 + 144) = v15;
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(
      retaddr,
      172,
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
      2147549183LL);
    v17 = *(_QWORD *)(*(_QWORD *)(a1 + 96) + 208LL);
    v54[0] = v17;
    if ( v17 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
    wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(
      retaddr,
      175,
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
      2147549183LL);
    v18 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v17 + 80LL);
    v19 = (_QWORD *)(a1 + 152);
    v20 = *(_QWORD *)(a1 + 152);
    *(_QWORD *)(a1 + 152) = 0;
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v18(v17, a1 + 152);
    if ( *v19 )
    {
      if ( (unsigned int)dword_1800C1058 > 5 )
      {
        v23 = *(_QWORD *)(a1 + 96);
        *(_QWORD *)v53 = v23 + 112;
        LODWORD(v56) = *(_DWORD *)(*(_QWORD *)(v23 + 104) + 136LL);
        v57 = *(_DWORD *)(v23 + 128);
        v52 = "Getting Media Clock Timestamp";
        v51 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::ICpuFrameProcessor,struct Rdp::Avenc::ICpuFrameAsyn"
              "cProcessor>::Start";
        LODWORD(v58) = 187;
        v50 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
          (unsigned int)&dword_1800C1058,
          (unsigned int)word_1800B0F22,
          v21,
          v22,
          (__int64)&v50,
          (__int64)&v58,
          (__int64)&v51,
          (__int64)&v52,
          (__int64)&v57,
          (__int64)&v56,
          (__int64)v53);
      }
      v24 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v19 + 24LL))(*v19);
      if ( (unsigned int)dword_1800C1058 > 5 )
      {
        *(_QWORD *)v53 = v24;
        v27 = *(_QWORD *)(a1 + 96);
        v52 = (const char *)(v27 + 112);
        LODWORD(v56) = *(_DWORD *)(*(_QWORD *)(v27 + 104) + 136LL);
        v57 = *(_DWORD *)(v27 + 128);
        v51 = "Media Clock Timestamp retrieved";
        v50 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::ICpuFrameProcessor,struct Rdp::Avenc::ICpuFrameAsyn"
              "cProcessor>::Start";
        LODWORD(v58) = 198;
        v49 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_1800C1058,
          (unsigned int)&word_1800B0DFE,
          v25,
          v26,
          (__int64)&v49,
          (__int64)&v58,
          (__int64)&v50,
          (__int64)&v51,
          (__int64)&v57,
          (__int64)&v56,
          (__int64)&v52,
          (__int64)v53);
      }
    }
    else if ( (unsigned int)dword_1800C1058 > 5 )
    {
      v28 = *(_QWORD *)(a1 + 96);
      *(_QWORD *)v53 = v28 + 112;
      LODWORD(v56) = *(_DWORD *)(*(_QWORD *)(v28 + 104) + 136LL);
      v57 = *(_DWORD *)(v28 + 128);
      v52 = "No media clock available";
      v51 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::ICpuFrameProcessor,struct Rdp::Avenc::ICpuFrameAsyncP"
            "rocessor>::Start";
      LODWORD(v58) = 208;
      v50 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)word_1800B0E62,
        v21,
        v22,
        (__int64)&v50,
        (__int64)&v58,
        (__int64)&v51,
        (__int64)&v52,
        (__int64)&v57,
        (__int64)&v56,
        (__int64)v53);
    }
    started = Rdp::Avenc::Ic3::CDsGfxChannel::SendStartStreamPdu(
                *(Rdp::Avenc::Ic3::CDsGfxChannel **)(a1 + 144),
                (const struct _GUID *)(*(_QWORD *)(a1 + 96) + 112LL),
                *(_DWORD *)(*(_QWORD *)(a1 + 96) + 128LL),
                *(_DWORD *)(*(_QWORD *)(a1 + 96) + 140LL),
                *(_DWORD *)(*(_QWORD *)(a1 + 96) + 144LL),
                (const struct tagRECT *)(*(_QWORD *)(a1 + 96) + 176LL));
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0xDA,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
      (const char *)started,
      (int)"Unable to send start stream pdu.",
      (const char *)v47);
    if ( *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a1 + 96) + 104LL) + 288LL) )
    {
      *(_BYTE *)(a1 + 352) = 0;
      v32 = operator new(8u);
      *v32 = a1 - 80;
      v56 = v32;
      v48 = (struct tagRECT *)&v53[2];
      v45 = 0;
      v33 = _o__beginthreadex(
              0,
              0,
              ____Invoke_V__tuple_V_lambda_1___CO___Start___CIc3FrameProcessor_UICpuFrameProcessor_Avenc_Rdp__UICpuFrameAsyncProcessor_23__Ic3_Avenc_Rdp__UEAAJXZ__std___0A__thread_std__CAIPEAX_Z,
              v32);
      *(_QWORD *)v53 = v33;
      if ( !v33 )
      {
        v53[2] = 0;
        std::_Throw_Cpp_error(6);
      }
      if ( *(_DWORD *)(a1 + 336) )
      {
        _o_terminate(v34, v33);
        __debugbreak();
      }
      v35 = v53[2];
      v36 = v53[3];
      *(_OWORD *)v53 = 0;
      *(_QWORD *)(a1 + 328) = v33;
      *(_DWORD *)(a1 + 336) = v35;
      *(_DWORD *)(a1 + 340) = v36;
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
        v45,
        (int)v48,
        11,
        &WPP_82575e15b34e32cfad750d208edc4dfe_Traceguids,
        v38);
    }
    if ( (unsigned int)dword_1800C1058 > 5 )
    {
      v41 = *(_QWORD *)(a1 + 96);
      v54[0] = v41 + 112;
      LODWORD(v56) = *(_DWORD *)(*(_QWORD *)(v41 + 104) + 136LL);
      v57 = *(_DWORD *)(v41 + 128);
      *(_QWORD *)v53 = "StartFrameProcessorDone";
      v52 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::ICpuFrameProcessor,struct Rdp::Avenc::ICpuFrameAsyncP"
            "rocessor>::Start";
      LODWORD(v58) = 234;
      v51 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)word_1800B0D1A,
        v30,
        v31,
        (__int64)&v51,
        (__int64)&v58,
        (__int64)&v52,
        (__int64)v53,
        (__int64)&v57,
        (__int64)&v56,
        (__int64)v54);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xEE,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
                           v42);
  }
  return result;
}

```

## disassembly

```asm
0x18004adb0  mov     [rsp+arg_0], rbx
0x18004adb5  push    rsi
0x18004adb6  push    rdi
0x18004adb7  push    r12
0x18004adb9  push    r14
0x18004adbb  push    r15
0x18004adbd  sub     rsp, 0B0h
0x18004adc4  mov     rbx, rcx
0x18004adc7  lea     rcx, WPP_GLOBAL_Control
0x18004adce  mov     rax, cs:WPP_GLOBAL_Control
0x18004add5  mov     sil, 1
0x18004add8  cmp     rax, rcx
0x18004addb  jz      short loc_18004ADEE
0x18004addd  test    [rax+1Ch], sil
0x18004ade1  jz      short loc_18004ADEE
0x18004ade3  cmp     byte ptr [rax+19h], 4
0x18004ade7  jb      short loc_18004ADEE
0x18004ade9  mov     dil, sil
0x18004adec  jmp     short loc_18004ADF1
0x18004adee  xor     dil, dil
0x18004adf1  lea     rax, WPP_RECORDER_INITIALIZED
0x18004adf8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18004adff  setnz   r14b
0x18004ae03  test    dil, dil
0x18004ae06  jnz     short loc_18004AE0D
0x18004ae08  test    r14b, r14b
0x18004ae0b  jz      short loc_18004AE44
0x18004ae0d  call    cs:__imp_GetCurrentThreadId
0x18004ae13  mov     dword ptr [rsp+0D8h+var_98], eax; char
0x18004ae17  lea     r15, WPP_82575e15b34e32cfad750d208edc4dfe_Traceguids
0x18004ae1e  mov     [rsp+0D8h+MessageGuid], r15; MessageGuid
0x18004ae23  mov     [rsp+0D8h+var_A8], 0Ah; __int16
0x18004ae2a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ae31  mov     r9, [rcx+28h]; int
0x18004ae35  mov     r8b, r14b; int
0x18004ae38  mov     dl, dil; int
0x18004ae3b  mov     rcx, [rcx+10h]; int
0x18004ae3f  call    WPP_RECORDER_AND_TRACE_SF_D
0x18004ae44  mov     eax, cs:dword_1800C1058
0x18004ae4a  cmp     eax, 4
0x18004ae4d  jbe     loc_18004AF84
0x18004ae53  mov     rcx, cs:qword_1800C1070
0x18004ae5a  mov     rax, cs:qword_1800C1068
0x18004ae61  mov     rdx, 470000000000h
0x18004ae6b  test    rdx, rax
0x18004ae6e  jz      loc_18004AF84
0x18004ae74  mov     rax, rcx
0x18004ae77  and     rax, rdx
0x18004ae7a  cmp     rax, rcx
0x18004ae7d  jnz     loc_18004AF84
0x18004ae83  mov     rdx, [rbx+60h]
0x18004ae87  lea     rax, [rdx+70h]
0x18004ae8b  mov     [rsp+0D8h+arg_18], rax
0x18004ae93  mov     rax, [rdx+68h]
0x18004ae97  mov     ecx, [rax+88h]
0x18004ae9d  mov     dword ptr [rsp+0D8h+arg_8], ecx
0x18004aea4  mov     eax, [rdx+80h]
0x18004aeaa  mov     [rsp+0D8h+arg_10], eax
0x18004aeb1  lea     rax, aStartIc3FrameP; "Start Ic3 frame processor"
0x18004aeb8  mov     [rsp+0D8h+var_68], rax
0x18004aebd  lea     rax, xmmword_1800C21A0
0x18004aec4  mov     [rsp+0D8h+var_60], rax
0x18004aec9  lea     rax, aDirectstreamme; "DirectStreamMedia_Service"
0x18004aed0  mov     [rsp+0D8h+var_58], rax
0x18004aed8  lea     rax, aRdpavenc; "RdpAvenc"
0x18004aedf  mov     [rsp+0D8h+var_50], rax
0x18004aee7  mov     qword ptr [rsp+0D8h+var_48], 1000000h
0x18004aef3  lea     rax, aCheckpoint; "Checkpoint"
0x18004aefa  mov     [rsp+0D8h+var_38], rax
0x18004af02  lea     rax, [rsp+0D8h+arg_18]
0x18004af0a  mov     [rsp+0D8h+var_78], rax
0x18004af0f  lea     rax, [rsp+0D8h+arg_8]
0x18004af17  mov     [rsp+0D8h+var_80], rax
0x18004af1c  lea     rax, [rsp+0D8h+arg_10]
0x18004af24  mov     [rsp+0D8h+var_88], rax
0x18004af29  lea     rax, [rsp+0D8h+var_68]
0x18004af2e  mov     [rsp+0D8h+var_90], rax
0x18004af33  lea     rax, [rsp+0D8h+var_60]
0x18004af38  mov     qword ptr [rsp+0D8h+var_98], rax
0x18004af3d  lea     rax, [rsp+0D8h+var_58]
0x18004af45  mov     [rsp+0D8h+MessageGuid], rax
0x18004af4a  lea     rax, [rsp+0D8h+var_50]
0x18004af52  mov     qword ptr [rsp+0D8h+var_A8], rax
0x18004af57  lea     rax, [rsp+0D8h+var_48]
0x18004af5f  mov     [rsp+0D8h+var_B0], rax
0x18004af64  lea     rax, [rsp+0D8h+var_38]
0x18004af6c  mov     qword ptr [rsp+0D8h+var_B8], rax
0x18004af71  lea     rdx, word_1800B0FE2
0x18004af78  lea     rcx, dword_1800C1058
0x18004af7f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U4@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@33AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@65@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x18004af84  mov     [rsp+0D8h+var_B8], 0A0h; unsigned int
0x18004af8c  lea     r14, aOnecoreuapTerm_23; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18004af93  mov     r9, r14; char *
0x18004af96  lea     rdi, aRdpAvencIc3Cic; "Rdp::Avenc::Ic3::CIc3FrameProcessor<str"...
0x18004af9d  mov     r8, rdi; char *
0x18004afa0  lea     rdx, aIc3frameproces; "Ic3FrameProcessorStart"
0x18004afa7  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18004afae  call    ?push0@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1I@Z; Rdp::Modern::Utils::CInflightRecorder::push0(ushort const *,char const *,char const *,uint)
0x18004afb3  mov     eax, cs:dword_1800C1058
0x18004afb9  cmp     eax, 5
0x18004afbc  jbe     loc_18004B088
0x18004afc2  mov     rdx, [rbx+60h]
0x18004afc6  lea     rax, [rdx+70h]
0x18004afca  mov     [rsp+0D8h+var_38], rax
0x18004afd2  mov     rax, [rdx+68h]
0x18004afd6  mov     ecx, [rax+88h]
0x18004afdc  mov     dword ptr [rsp+0D8h+arg_8], ecx
0x18004afe3  mov     eax, [rdx+80h]
0x18004afe9  mov     [rsp+0D8h+arg_10], eax
0x18004aff0  lea     rax, aStartframeproc_1; "StartFrameProcessor"
0x18004aff7  mov     qword ptr [rsp+0D8h+var_48], rax
0x18004afff  mov     [rsp+0D8h+var_50], rdi
0x18004b007  mov     dword ptr [rsp+0D8h+arg_18], 0A8h
0x18004b012  mov     [rsp+0D8h+var_58], r14
0x18004b01a  lea     rax, [rsp+0D8h+var_38]
0x18004b022  mov     [rsp+0D8h+var_88], rax
0x18004b027  lea     rax, [rsp+0D8h+arg_8]
0x18004b02f  mov     [rsp+0D8h+var_90], rax
0x18004b034  lea     rax, [rsp+0D8h+arg_10]
0x18004b03c  mov     qword ptr [rsp+0D8h+var_98], rax
0x18004b041  lea     rax, [rsp+0D8h+var_48]
0x18004b049  mov     [rsp+0D8h+MessageGuid], rax
0x18004b04e  lea     rax, [rsp+0D8h+var_50]
0x18004b056  mov     qword ptr [rsp+0D8h+var_A8], rax
0x18004b05b  lea     rax, [rsp+0D8h+arg_18]
0x18004b063  mov     [rsp+0D8h+var_B0], rax
0x18004b068  lea     rax, [rsp+0D8h+var_58]
0x18004b070  mov     qword ptr [rsp+0D8h+var_B8], rax
0x18004b075  lea     rdx, word_1800B0EC2
0x18004b07c  lea     rcx, dword_1800C1058
0x18004b083  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x18004b088  lea     r15, [rbx+90h]
0x18004b08f  mov     rax, [rbx+60h]
0x18004b093  mov     rcx, [rax+0C8h]
0x18004b09a  mov     rdi, [r15]
0x18004b09d  mov     [r15], rcx
0x18004b0a0  test    rcx, rcx
0x18004b0a3  jz      short loc_18004B0B1
0x18004b0a5  mov     rax, [rcx]
0x18004b0a8  mov     rax, [rax+8]
0x18004b0ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b0b1  test    rdi, rdi
0x18004b0b4  jz      short loc_18004B0C6
0x18004b0b6  mov     rax, [rdi]
0x18004b0b9  mov     rcx, rdi
0x18004b0bc  mov     rax, [rax+10h]
0x18004b0c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b0c5  nop
0x18004b0c6  mov     rcx, [rsp+0D8h]
0x18004b0ce  lea     rax, aUnableToRetrie_0; "Unable to retrieve DS GFX channel."
0x18004b0d5  mov     [rsp+0D8h+var_B0], rax
0x18004b0da  mov     qword ptr [rsp+0D8h+var_B8], r15
0x18004b0df  mov     r12d, 8000FFFFh
0x18004b0e5  mov     r9d, r12d
0x18004b0e8  mov     r8, r14
0x18004b0eb  mov     edx, 0ACh
0x18004b0f0  call    ??$Throw_HrIfNullMsg@V?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@wil@@$0A@@in1diag3@details@wil@@YAXPEAXIPEBDJAEBV?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@2@1ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(void *,uint,char const *,long,wil::com_ptr_t<IPropertyStore,wil::err_exception_policy> const &,char const *,...)
0x18004b0f5  mov     rax, [rbx+60h]
0x18004b0f9  mov     rdi, [rax+0D0h]
0x18004b100  mov     [rsp+0D8h+var_38], rdi
0x18004b108  test    rdi, rdi
0x18004b10b  jz      short loc_18004B11D
0x18004b10d  mov     rax, [rdi]
0x18004b110  mov     rcx, rdi
0x18004b113  mov     rax, [rax+8]
0x18004b117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b11c  nop
0x18004b11d  mov     rcx, [rsp+0D8h]
0x18004b125  lea     rax, aUnableToRetrie; "Unable to retrieve DS media control."
0x18004b12c  mov     [rsp+0D8h+var_B0], rax
0x18004b131  lea     rax, [rsp+0D8h+var_38]
0x18004b139  mov     qword ptr [rsp+0D8h+var_B8], rax
0x18004b13e  mov     r9d, r12d
0x18004b141  mov     r8, r14
0x18004b144  mov     edx, 0AFh
0x18004b149  call    ??$Throw_HrIfNullMsg@V?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@wil@@$0A@@in1diag3@details@wil@@YAXPEAXIPEBDJAEBV?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@2@1ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(void *,uint,char const *,long,wil::com_ptr_t<IPropertyStore,wil::err_exception_policy> const &,char const *,...)
0x18004b14e  mov     rax, [rdi]
0x18004b151  mov     r12, [rax+50h]
0x18004b155  lea     r14, [rbx+98h]
0x18004b15c  mov     rcx, [r14]
0x18004b15f  mov     qword ptr [r14], 0
0x18004b166  test    rcx, rcx
0x18004b169  jz      short loc_18004B178
0x18004b16b  mov     rdx, [rcx]
0x18004b16e  mov     rax, [rdx+10h]
0x18004b172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b177  nop
0x18004b178  mov     rdx, r14
0x18004b17b  mov     rcx, rdi
0x18004b17e  mov     rax, r12
0x18004b181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b186  xor     r12d, r12d
0x18004b189  cmp     [r14], r12
0x18004b18c  mov     eax, cs:dword_1800C1058
0x18004b192  jz      loc_18004B36F
0x18004b198  cmp     eax, 5
0x18004b19b  jbe     loc_18004B26F
0x18004b1a1  mov     rdx, [rbx+60h]
0x18004b1a5  lea     rax, [rdx+70h]
0x18004b1a9  mov     qword ptr [rsp+0D8h+var_48], rax
0x18004b1b1  mov     rax, [rdx+68h]
0x18004b1b5  mov     ecx, [rax+88h]
0x18004b1bb  mov     dword ptr [rsp+0D8h+arg_8], ecx
0x18004b1c2  mov     eax, [rdx+80h]
0x18004b1c8  mov     [rsp+0D8h+arg_10], eax
0x18004b1cf  lea     rax, aGettingMediaCl; "Getting Media Clock Timestamp"
0x18004b1d6  mov     [rsp+0D8h+var_50], rax
0x18004b1de  lea     rax, aRdpAvencIc3Cic; "Rdp::Avenc::Ic3::CIc3FrameProcessor<str"...
0x18004b1e5  mov     [rsp+0D8h+var_58], rax
0x18004b1ed  mov     dword ptr [rsp+0D8h+arg_18], 0BBh
0x18004b1f8  lea     rax, aOnecoreuapTerm_23; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18004b1ff  mov     [rsp+0D8h+var_60], rax
0x18004b204  lea     rax, [rsp+0D8h+var_48]
0x18004b20c  mov     [rsp+0D8h+var_88], rax
0x18004b211  lea     rax, [rsp+0D8h+arg_8]
0x18004b219  mov     [rsp+0D8h+var_90], rax
0x18004b21e  lea     rax, [rsp+0D8h+arg_10]
0x18004b226  mov     qword ptr [rsp+0D8h+var_98], rax
0x18004b22b  lea     rax, [rsp+0D8h+var_50]
0x18004b233  mov     [rsp+0D8h+MessageGuid], rax
0x18004b238  lea     rax, [rsp+0D8h+var_58]
0x18004b240  mov     qword ptr [rsp+0D8h+var_A8], rax
0x18004b245  lea     rax, [rsp+0D8h+arg_18]
0x18004b24d  mov     [rsp+0D8h+var_B0], rax
0x18004b252  lea     rax, [rsp+0D8h+var_60]
0x18004b257  mov     qword ptr [rsp+0D8h+var_B8], rax
0x18004b25c  lea     rdx, word_1800B0F22
0x18004b263  lea     rcx, dword_1800C1058
0x18004b26a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x18004b26f  mov     rcx, [r14]
0x18004b272  mov     rax, [rcx]
0x18004b275  mov     rax, [rax+18h]
0x18004b279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b27e  mov     ecx, cs:dword_1800C1058
0x18004b284  cmp     ecx, 5
0x18004b287  jbe     loc_18004B446
0x18004b28d  mov     qword ptr [rsp+0D8h+var_48], rax
0x18004b295  mov     rdx, [rbx+60h]
0x18004b299  lea     rax, [rdx+70h]
0x18004b29d  mov     [rsp+0D8h+var_50], rax
0x18004b2a5  mov     rax, [rdx+68h]
0x18004b2a9  mov     ecx, [rax+88h]
0x18004b2af  mov     dword ptr [rsp+0D8h+arg_8], ecx
0x18004b2b6  mov     eax, [rdx+80h]
0x18004b2bc  mov     [rsp+0D8h+arg_10], eax
0x18004b2c3  lea     rax, aMediaClockTime; "Media Clock Timestamp retrieved"
0x18004b2ca  mov     [rsp+0D8h+var_58], rax
0x18004b2d2  lea     rax, aRdpAvencIc3Cic; "Rdp::Avenc::Ic3::CIc3FrameProcessor<str"...
0x18004b2d9  mov     [rsp+0D8h+var_60], rax
0x18004b2de  mov     dword ptr [rsp+0D8h+arg_18], 0C6h
0x18004b2e9  lea     rax, aOnecoreuapTerm_23; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18004b2f0  mov     [rsp+0D8h+var_68], rax
0x18004b2f5  lea     rax, [rsp+0D8h+var_48]
0x18004b2fd  mov     [rsp+0D8h+var_80], rax
0x18004b302  lea     rax, [rsp+0D8h+var_50]
0x18004b30a  mov     [rsp+0D8h+var_88], rax
0x18004b30f  lea     rax, [rsp+0D8h+arg_8]
0x18004b317  mov     [rsp+0D8h+var_90], rax
0x18004b31c  lea     rax, [rsp+0D8h+arg_10]
0x18004b324  mov     qword ptr [rsp+0D8h+var_98], rax
0x18004b329  lea     rax, [rsp+0D8h+var_58]
0x18004b331  mov     [rsp+0D8h+MessageGuid], rax
0x18004b336  lea     rax, [rsp+0D8h+var_60]
0x18004b33b  mov     qword ptr [rsp+0D8h+var_A8], rax
0x18004b340  lea     rax, [rsp+0D8h+arg_18]
0x18004b348  mov     [rsp+0D8h+var_B0], rax
0x18004b34d  lea     rax, [rsp+0D8h+var_68]
0x18004b352  mov     qword ptr [rsp+0D8h+var_B8], rax
0x18004b357  lea     rdx, word_1800B0DFE
0x18004b35e  lea     rcx, dword_1800C1058
0x18004b365  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &)
0x18004b36a  jmp     loc_18004B446
0x18004b36f  cmp     eax, 5
0x18004b372  jbe     loc_18004B446
0x18004b378  mov     rdx, [rbx+60h]
0x18004b37c  lea     rax, [rdx+70h]
0x18004b380  mov     qword ptr [rsp+0D8h+var_48], rax
0x18004b388  mov     rax, [rdx+68h]
0x18004b38c  mov     ecx, [rax+88h]
0x18004b392  mov     dword ptr [rsp+0D8h+arg_8], ecx
0x18004b399  mov     eax, [rdx+80h]
0x18004b39f  mov     [rsp+0D8h+arg_10], eax
0x18004b3a6  lea     rax, aNoMediaClockAv; "No media clock available"
0x18004b3ad  mov     [rsp+0D8h+var_50], rax
0x18004b3b5  lea     rax, aRdpAvencIc3Cic; "Rdp::Avenc::Ic3::CIc3FrameProcessor<str"...
0x18004b3bc  mov     [rsp+0D8h+var_58], rax
0x18004b3c4  mov     dword ptr [rsp+0D8h+arg_18], 0D0h
0x18004b3cf  lea     rax, aOnecoreuapTerm_23; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18004b3d6  mov     [rsp+0D8h+var_60], rax
0x18004b3db  lea     rax, [rsp+0D8h+var_48]
0x18004b3e3  mov     [rsp+0D8h+var_88], rax
0x18004b3e8  lea     rax, [rsp+0D8h+arg_8]
0x18004b3f0  mov     [rsp+0D8h+var_90], rax
0x18004b3f5  lea     rax, [rsp+0D8h+arg_10]
0x18004b3fd  mov     qword ptr [rsp+0D8h+var_98], rax
0x18004b402  lea     rax, [rsp+0D8h+var_50]
0x18004b40a  mov     [rsp+0D8h+MessageGuid], rax
0x18004b40f  lea     rax, [rsp+0D8h+var_58]
0x18004b417  mov     qword ptr [rsp+0D8h+var_A8], rax
0x18004b41c  lea     rax, [rsp+0D8h+arg_18]
  ... truncated ...
```
