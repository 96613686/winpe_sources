# Rdp::Avenc::Umrdp::CCpuFrameProcessor::SetRenderDevice(ID3D11Device *)

- ea: `0x18001db90`
- end: `0x18001e02b`
- name: `?SetRenderDevice@CCpuFrameProcessor@Umrdp@Avenc@Rdp@@UEAAJPEAUID3D11Device@@@Z`
- size: `1179`
- prototype: `__int64 __fastcall(Rdp::Avenc::Umrdp::CCpuFrameProcessor *__hidden this, struct ID3D11Device *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180001f30`
- `0x1800153f8`
- `0x180015480`
- `0x18001cbcc`
- `0x18001d290`
- `0x18001db90`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001dbf3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001dfe0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001dbf3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001dfe0`

## string_xrefs

- `0x18001ded5`: `SetRenderDevice: create new RdpSurface`
- `0x18001df91`: `SetRenderDevice: create new RdpSurface. Id %d`
- `0x18001dcbd`: `Recreate Rdp surface because it is incompatible with monitor size`
- `0x18001dd76`: `Recreate Rdp surface. Id %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Rdp::Avenc::Umrdp::CCpuFrameProcessor::SetRenderDevice(
        Rdp::Avenc::Umrdp::CCpuFrameProcessor *this,
        struct ID3D11Device *a2,
        int a3,
        int a4)
{
  char v6; // bl
  bool v7; // r14
  bool v8; // r15
  char CurrentThreadId; // al
  int v10; // r8d
  int v11; // edx
  __int64 v12; // r14
  Rdp::Avenc::Umrdp::CCpuFrameProcessor *v13; // r14
  __int64 v14; // rcx
  char *v15; // r12
  int v16; // r8d
  int v17; // r9d
  __int64 v18; // rdx
  const char *v19; // r9
  __int64 v20; // rdx
  __int64 v21; // rdx
  bool v22; // di
  char v23; // al
  int v24; // r8d
  int v25; // edx
  __int64 result; // rax
  int v27; // [rsp+20h] [rbp-78h]
  int v28; // [rsp+20h] [rbp-78h]
  int v29; // [rsp+28h] [rbp-70h]
  int v30; // [rsp+28h] [rbp-70h]
  const char *v31; // [rsp+50h] [rbp-48h] BYREF
  _QWORD v32[8]; // [rsp+58h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  int v34; // [rsp+A0h] [rbp+8h] BYREF
  int v35; // [rsp+A8h] [rbp+10h] BYREF
  int v36; // [rsp+B0h] [rbp+18h] BYREF
  const char *v37; // [rsp+B8h] [rbp+20h] BYREF

  v6 = 1;
  v7 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v8 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v10) = v8;
    LOBYTE(v11) = v7;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      v10,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v27,
      v29,
      16,
      &WPP_19b31c027c473e795a0f5fbb7cb41a6c_Traceguids,
      CurrentThreadId);
  }
  try
  {
    v12 = *((_QWORD *)this + 5);
    *((_QWORD *)this + 5) = a2;
    if ( a2 )
      ((void (__fastcall *)(struct ID3D11Device *))a2->lpVtbl->AddRef)(a2);
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v13 = (Rdp::Avenc::Umrdp::CCpuFrameProcessor *)((char *)this - 80);
    v14 = *((_QWORD *)this + 2);
    if ( v14 )
    {
      v15 = (char *)this + 32;
      if ( (*(unsigned __int8 (__fastcall **)(__int64, char *, char *))(*(_QWORD *)v14 + 24LL))(
             v14,
             (char *)this + 40,
             (char *)this + 32) )
      {
        if ( (unsigned int)dword_1800C1058 > 4 )
        {
          v20 = *(_QWORD *)v15;
          v34 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v15 + 120LL) + 196LL);
          v35 = *(_DWORD *)(v20 + 128);
          v37 = "SetRenderDevice: re-use RdpSurface";
          v32[0] = "Rdp::Avenc::Umrdp::CCpuFrameProcessor::SetRenderDevice";
          v36 = 673;
          v31 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\frameprocessor.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_1800C1058,
            (unsigned int)byte_1800AD59D,
            v16,
            v17,
            (__int64)&v31,
            (__int64)&v36,
            (__int64)v32,
            (__int64)&v37,
            (__int64)&v35,
            (__int64)&v34);
        }
        v30 = *(_DWORD *)(*(_QWORD *)v15 + 128LL);
        Rdp::Modern::Utils::CInflightRecorder::pushN(
          (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
          (wchar_t *)L"SetRenderDevice: re-use RdpSurface. Id %d",
          "Rdp::Avenc::Umrdp::CCpuFrameProcessor::SetRenderDevice",
          "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\frameprocessor.cpp",
          0x2A4u);
      }
      else
      {
        if ( (unsigned int)dword_1800C1058 > 4 )
        {
          v18 = *(_QWORD *)v15;
          v34 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v15 + 120LL) + 196LL);
          v35 = *(_DWORD *)(v18 + 128);
          v37 = "Recreate Rdp surface because it is incompatible with monitor size";
          v31 = "Rdp::Avenc::Umrdp::CCpuFrameProcessor::SetRenderDevice";
          v36 = 654;
          v32[0] = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\frameprocessor.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_1800C1058,
            (unsigned int)word_1800AD5F2,
            v16,
            v17,
            (__int64)v32,
            (__int64)&v36,
            (__int64)&v31,
            (__int64)&v37,
            (__int64)&v35,
            (__int64)&v34);
        }
        v30 = *(_DWORD *)(*(_QWORD *)v15 + 128LL);
        Rdp::Modern::Utils::CInflightRecorder::pushN(
          (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
          (wchar_t *)L"Recreate Rdp surface. Id %d",
          "Rdp::Avenc::Umrdp::CCpuFrameProcessor::SetRenderDevice",
          "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\frameprocessor.cpp",
          0x291u);
        Rdp::Avenc::Umrdp::CFrameProcessor<Rdp::Avenc::ICpuFrameProcessor,Rdp::Avenc::Umrdp::IUmrdpFrameProcessorRailPrivate>::DestroyRdpSurface(v13);
        Rdp::Avenc::Umrdp::CCpuFrameProcessor::CreateRdpSurface(v13);
      }
    }
    else
    {
      if ( (unsigned int)dword_1800C1058 > 4 )
      {
        v21 = *((_QWORD *)this + 4);
        v34 = *(_DWORD *)(*(_QWORD *)(v21 + 120) + 196LL);
        v35 = *(_DWORD *)(v21 + 128);
        v37 = "SetRenderDevice: create new RdpSurface";
        v32[0] = "Rdp::Avenc::Umrdp::CCpuFrameProcessor::SetRenderDevice";
        v36 = 689;
        v31 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\frameprocessor.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1800C1058,
          (unsigned int)qword_1800AD548,
          a3,
          a4,
          (__int64)&v31,
          (__int64)&v36,
          (__int64)v32,
          (__int64)&v37,
          (__int64)&v35,
          (__int64)&v34);
      }
      v30 = *(_DWORD *)(*((_QWORD *)this + 4) + 128LL);
      Rdp::Modern::Utils::CInflightRecorder::pushN(
        (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
        (wchar_t *)L"SetRenderDevice: create new RdpSurface. Id %d",
        "Rdp::Avenc::Umrdp::CCpuFrameProcessor::SetRenderDevice",
        "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\frameprocessor.cpp",
        0x2B4u);
      Rdp::Avenc::Umrdp::CCpuFrameProcessor::CreateRdpSurface(v13);
    }
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v6 = 0;
    }
    v22 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v23 = GetCurrentThreadId();
      LOBYTE(v24) = v22;
      LOBYTE(v25) = v6;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v25,
        v24,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v28,
        v30,
        17,
        &WPP_19b31c027c473e795a0f5fbb7cb41a6c_Traceguids,
        v23);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2BC,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\frameprocessor.cpp",
                           v19);
  }
  return result;
}

```

## disassembly

```asm
0x18001db90  push    rbx
0x18001db92  push    rsi
0x18001db93  push    rdi
0x18001db94  push    r12
0x18001db96  push    r13
0x18001db98  push    r14
0x18001db9a  push    r15
0x18001db9c  sub     rsp, 60h
0x18001dba0  mov     rdi, rdx
0x18001dba3  mov     rsi, rcx
0x18001dba6  lea     rcx, WPP_GLOBAL_Control
0x18001dbad  mov     rax, cs:WPP_GLOBAL_Control
0x18001dbb4  mov     bl, 1
0x18001dbb6  cmp     rax, rcx
0x18001dbb9  jz      short loc_18001DBCB
0x18001dbbb  test    [rax+1Ch], bl
0x18001dbbe  jz      short loc_18001DBCB
0x18001dbc0  cmp     byte ptr [rax+19h], 4
0x18001dbc4  jb      short loc_18001DBCB
0x18001dbc6  mov     r14b, bl
0x18001dbc9  jmp     short loc_18001DBCE
0x18001dbcb  xor     r14b, r14b
0x18001dbce  lea     r12, WPP_RECORDER_INITIALIZED
0x18001dbd5  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18001dbdc  setnz   r15b
0x18001dbe0  test    r14b, r14b
0x18001dbe3  jnz     short loc_18001DBF3
0x18001dbe5  test    r15b, r15b
0x18001dbe8  jnz     short loc_18001DBF3
0x18001dbea  lea     r13, WPP_19b31c027c473e795a0f5fbb7cb41a6c_Traceguids
0x18001dbf1  jmp     short loc_18001DC2A
0x18001dbf3  call    cs:__imp_GetCurrentThreadId
0x18001dbf9  mov     dword ptr [rsp+98h+var_58], eax; char
0x18001dbfd  lea     r13, WPP_19b31c027c473e795a0f5fbb7cb41a6c_Traceguids
0x18001dc04  mov     [rsp+98h+MessageGuid], r13; MessageGuid
0x18001dc09  mov     [rsp+98h+var_68], 10h; __int16
0x18001dc10  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dc17  mov     r9, [rcx+28h]; int
0x18001dc1b  mov     r8b, r15b; int
0x18001dc1e  mov     dl, r14b; int
0x18001dc21  mov     rcx, [rcx+10h]; int
0x18001dc25  call    WPP_RECORDER_AND_TRACE_SF_D
0x18001dc2a  lea     r15, [rsi+28h]
0x18001dc2e  mov     r14, [r15]
0x18001dc31  mov     [r15], rdi
0x18001dc34  test    rdi, rdi
0x18001dc37  jz      short loc_18001DC48
0x18001dc39  mov     rax, [rdi]
0x18001dc3c  mov     rcx, rdi
0x18001dc3f  mov     rax, [rax+8]
0x18001dc43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc48  test    r14, r14
0x18001dc4b  jz      short loc_18001DC5D
0x18001dc4d  mov     rax, [r14]
0x18001dc50  mov     rcx, r14
0x18001dc53  mov     rax, [rax+10h]
0x18001dc57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc5c  nop
0x18001dc5d  lea     r14, [rsi-50h]
0x18001dc61  mov     rcx, [r14+60h]
0x18001dc65  test    rcx, rcx
0x18001dc68  jz      loc_18001DEA1
0x18001dc6e  lea     r12, [rsi+20h]
0x18001dc72  mov     rax, [rcx]
0x18001dc75  mov     r8, r12
0x18001dc78  mov     rdx, r15
0x18001dc7b  mov     rax, [rax+18h]
0x18001dc7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc84  test    al, al
0x18001dc86  mov     eax, cs:dword_1800C1058
0x18001dc8c  jnz     loc_18001DD9E
0x18001dc92  cmp     eax, 4
0x18001dc95  jbe     loc_18001DD4C
0x18001dc9b  mov     rdx, [r12]
0x18001dc9f  mov     rax, [rdx+78h]
0x18001dca3  mov     ecx, [rax+0C4h]
0x18001dca9  mov     [rsp+98h+arg_0], ecx
0x18001dcb0  mov     eax, [rdx+80h]
0x18001dcb6  mov     [rsp+98h+arg_8], eax
0x18001dcbd  lea     rax, aRecreateRdpSur_0; "Recreate Rdp surface because it is inco"...
0x18001dcc4  mov     [rsp+98h+arg_18], rax
0x18001dccc  lea     rdi, aRdpAvencUmrdpC_21; "Rdp::Avenc::Umrdp::CCpuFrameProcessor::"...
0x18001dcd3  mov     [rsp+98h+var_48], rdi
0x18001dcd8  mov     [rsp+98h+arg_10], 28Eh
0x18001dce3  lea     rsi, aOnecoreuapTerm_56; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18001dcea  mov     [rsp+98h+var_40], rsi
0x18001dcef  lea     rax, [rsp+98h+arg_0]
0x18001dcf7  mov     [rsp+98h+var_50], rax
0x18001dcfc  lea     rax, [rsp+98h+arg_8]
0x18001dd04  mov     qword ptr [rsp+98h+var_58], rax
0x18001dd09  lea     rax, [rsp+98h+arg_18]
0x18001dd11  mov     [rsp+98h+MessageGuid], rax
0x18001dd16  lea     rax, [rsp+98h+var_48]
0x18001dd1b  mov     qword ptr [rsp+98h+var_68], rax
0x18001dd20  lea     rax, [rsp+98h+arg_10]
0x18001dd28  mov     qword ptr [rsp+98h+var_70], rax
0x18001dd2d  lea     rax, [rsp+98h+var_40]
0x18001dd32  mov     qword ptr [rsp+98h+var_78], rax
0x18001dd37  lea     rdx, word_1800AD5F2
0x18001dd3e  lea     rcx, dword_1800C1058
0x18001dd45  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001dd4a  jmp     short loc_18001DD5A
0x18001dd4c  lea     rdi, aRdpAvencUmrdpC_21; "Rdp::Avenc::Umrdp::CCpuFrameProcessor::"...
0x18001dd53  lea     rsi, aOnecoreuapTerm_56; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18001dd5a  mov     rax, [r12]
0x18001dd5e  mov     edx, [rax+80h]
0x18001dd64  mov     [rsp+98h+var_70], edx
0x18001dd68  mov     [rsp+98h+var_78], 291h; unsigned int
0x18001dd70  mov     r9, rsi; char *
0x18001dd73  mov     r8, rdi; char *
0x18001dd76  lea     rdx, aRecreateRdpSur; "Recreate Rdp surface. Id %d"
0x18001dd7d  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18001dd84  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18001dd89  mov     rcx, r14
0x18001dd8c  call    ?DestroyRdpSurface@?$CFrameProcessor@UICpuFrameProcessor@Avenc@Rdp@@UIUmrdpFrameProcessorRailPrivate@Umrdp@23@@Umrdp@Avenc@Rdp@@IEAAXXZ; Rdp::Avenc::Umrdp::CFrameProcessor<Rdp::Avenc::ICpuFrameProcessor,Rdp::Avenc::Umrdp::IUmrdpFrameProcessorRailPrivate>::DestroyRdpSurface(void)
0x18001dd91  mov     rcx, r14; this
0x18001dd94  call    ?CreateRdpSurface@CCpuFrameProcessor@Umrdp@Avenc@Rdp@@AEAAXXZ; Rdp::Avenc::Umrdp::CCpuFrameProcessor::CreateRdpSurface(void)
0x18001dd99  jmp     loc_18001DE95
0x18001dd9e  cmp     eax, 4
0x18001dda1  jbe     loc_18001DE58
0x18001dda7  mov     rdx, [r12]
0x18001ddab  mov     rax, [rdx+78h]
0x18001ddaf  mov     ecx, [rax+0C4h]
0x18001ddb5  mov     [rsp+98h+arg_0], ecx
0x18001ddbc  mov     eax, [rdx+80h]
0x18001ddc2  mov     [rsp+98h+arg_8], eax
0x18001ddc9  lea     rax, aSetrenderdevic_3; "SetRenderDevice: re-use RdpSurface"
0x18001ddd0  mov     [rsp+98h+arg_18], rax
0x18001ddd8  lea     rdi, aRdpAvencUmrdpC_21; "Rdp::Avenc::Umrdp::CCpuFrameProcessor::"...
0x18001dddf  mov     [rsp+98h+var_40], rdi
0x18001dde4  mov     [rsp+98h+arg_10], 2A1h
0x18001ddef  lea     rsi, aOnecoreuapTerm_56; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18001ddf6  mov     [rsp+98h+var_48], rsi
0x18001ddfb  lea     rax, [rsp+98h+arg_0]
0x18001de03  mov     [rsp+98h+var_50], rax
0x18001de08  lea     rax, [rsp+98h+arg_8]
0x18001de10  mov     qword ptr [rsp+98h+var_58], rax
0x18001de15  lea     rax, [rsp+98h+arg_18]
0x18001de1d  mov     [rsp+98h+MessageGuid], rax
0x18001de22  lea     rax, [rsp+98h+var_40]
0x18001de27  mov     qword ptr [rsp+98h+var_68], rax
0x18001de2c  lea     rax, [rsp+98h+arg_10]
0x18001de34  mov     qword ptr [rsp+98h+var_70], rax
0x18001de39  lea     rax, [rsp+98h+var_48]
0x18001de3e  mov     qword ptr [rsp+98h+var_78], rax
0x18001de43  lea     rdx, byte_1800AD59D
0x18001de4a  lea     rcx, dword_1800C1058
0x18001de51  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001de56  jmp     short loc_18001DE66
0x18001de58  lea     rdi, aRdpAvencUmrdpC_21; "Rdp::Avenc::Umrdp::CCpuFrameProcessor::"...
0x18001de5f  lea     rsi, aOnecoreuapTerm_56; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18001de66  mov     rax, [r12]
0x18001de6a  mov     ecx, [rax+80h]
0x18001de70  mov     [rsp+98h+var_70], ecx
0x18001de74  mov     [rsp+98h+var_78], 2A4h; unsigned int
0x18001de7c  mov     r9, rsi; char *
0x18001de7f  mov     r8, rdi; char *
0x18001de82  lea     rdx, aSetrenderdevic_1; "SetRenderDevice: re-use RdpSurface. Id "...
0x18001de89  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18001de90  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18001de95  lea     r12, WPP_RECORDER_INITIALIZED
0x18001de9c  jmp     loc_18001DFAC
0x18001dea1  mov     eax, cs:dword_1800C1058
0x18001dea7  cmp     eax, 4
0x18001deaa  jbe     loc_18001DF64
0x18001deb0  lea     r15, [rsi+20h]
0x18001deb4  mov     rdx, [r15]
0x18001deb7  mov     rax, [rdx+78h]
0x18001debb  mov     ecx, [rax+0C4h]
0x18001dec1  mov     [rsp+98h+arg_0], ecx
0x18001dec8  mov     eax, [rdx+80h]
0x18001dece  mov     [rsp+98h+arg_8], eax
0x18001ded5  lea     rax, aSetrenderdevic_0; "SetRenderDevice: create new RdpSurface"
0x18001dedc  mov     [rsp+98h+arg_18], rax
0x18001dee4  lea     rdi, aRdpAvencUmrdpC_21; "Rdp::Avenc::Umrdp::CCpuFrameProcessor::"...
0x18001deeb  mov     [rsp+98h+var_40], rdi
0x18001def0  mov     [rsp+98h+arg_10], 2B1h
0x18001defb  lea     rsi, aOnecoreuapTerm_56; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18001df02  mov     [rsp+98h+var_48], rsi
0x18001df07  lea     rax, [rsp+98h+arg_0]
0x18001df0f  mov     [rsp+98h+var_50], rax
0x18001df14  lea     rax, [rsp+98h+arg_8]
0x18001df1c  mov     qword ptr [rsp+98h+var_58], rax
0x18001df21  lea     rax, [rsp+98h+arg_18]
0x18001df29  mov     [rsp+98h+MessageGuid], rax
0x18001df2e  lea     rax, [rsp+98h+var_40]
0x18001df33  mov     qword ptr [rsp+98h+var_68], rax
0x18001df38  lea     rax, [rsp+98h+arg_10]
0x18001df40  mov     qword ptr [rsp+98h+var_70], rax
0x18001df45  lea     rax, [rsp+98h+var_48]
0x18001df4a  mov     qword ptr [rsp+98h+var_78], rax
0x18001df4f  lea     rdx, qword_1800AD548
0x18001df56  lea     rcx, dword_1800C1058
0x18001df5d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001df62  jmp     short loc_18001DF76
0x18001df64  lea     r15, [rsi+20h]
0x18001df68  lea     rdi, aRdpAvencUmrdpC_21; "Rdp::Avenc::Umrdp::CCpuFrameProcessor::"...
0x18001df6f  lea     rsi, aOnecoreuapTerm_56; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18001df76  mov     rax, [r15]
0x18001df79  mov     ecx, [rax+80h]
0x18001df7f  mov     [rsp+98h+var_70], ecx; int
0x18001df83  mov     [rsp+98h+var_78], 2B4h; int
0x18001df8b  mov     r9, rsi; char *
0x18001df8e  mov     r8, rdi; char *
0x18001df91  lea     rdx, aSetrenderdevic_2; "SetRenderDevice: create new RdpSurface."...
0x18001df98  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18001df9f  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18001dfa4  mov     rcx, r14; this
0x18001dfa7  call    ?CreateRdpSurface@CCpuFrameProcessor@Umrdp@Avenc@Rdp@@AEAAXXZ; Rdp::Avenc::Umrdp::CCpuFrameProcessor::CreateRdpSurface(void)
0x18001dfac  mov     rax, cs:WPP_GLOBAL_Control
0x18001dfb3  lea     rcx, WPP_GLOBAL_Control
0x18001dfba  cmp     rax, rcx
0x18001dfbd  jz      short loc_18001DFCA
0x18001dfbf  test    [rax+1Ch], bl
0x18001dfc2  jz      short loc_18001DFCA
0x18001dfc4  cmp     byte ptr [rax+19h], 4
0x18001dfc8  jnb     short loc_18001DFCC
0x18001dfca  xor     bl, bl
0x18001dfcc  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18001dfd3  setnz   dil
0x18001dfd7  test    bl, bl
0x18001dfd9  jnz     short loc_18001DFE0
0x18001dfdb  test    dil, dil
0x18001dfde  jz      short loc_18001E00F
0x18001dfe0  call    cs:__imp_GetCurrentThreadId
0x18001dfe6  mov     dword ptr [rsp+98h+var_58], eax; char
0x18001dfea  mov     [rsp+98h+MessageGuid], r13; MessageGuid
0x18001dfef  mov     [rsp+98h+var_68], 11h; __int16
0x18001dff6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dffd  mov     r9, [rcx+28h]; int
0x18001e001  mov     r8b, dil; int
0x18001e004  mov     dl, bl; int
0x18001e006  mov     rcx, [rcx+10h]; int
0x18001e00a  call    WPP_RECORDER_AND_TRACE_SF_D
0x18001e00f  xor     eax, eax
0x18001e011  jmp     short loc_18001E01A
0x18001e013  mov     eax, [rsp+98h+arg_0]
0x18001e01a  add     rsp, 60h
0x18001e01e  pop     r15
0x18001e020  pop     r14
0x18001e022  pop     r13
0x18001e024  pop     r12
0x18001e026  pop     rdi
0x18001e027  pop     rsi
0x18001e028  pop     rbx
0x18001e029  retn
```
