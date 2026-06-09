# Rdp::Avenc::Yuv::CYuvProcessor::Stop(void)

- ea: `0x18005c770`
- end: `0x18005c9fd`
- name: `?Stop@CYuvProcessor@Yuv@Avenc@Rdp@@UEAAJXZ`
- size: `653`
- prototype: `__int64 __fastcall(Rdp::Avenc::Yuv::CYuvProcessor *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180003c64`
- `0x1800146bc`
- `0x1800152c4`
- `0x180015480`
- `0x18005c770`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005c7d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005c9af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005c7d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005c9af`

## pseudocode

```c
__int64 __fastcall Rdp::Avenc::Yuv::CYuvProcessor::Stop(Rdp::Avenc::Yuv::CYuvProcessor *this)
{
  char v2; // bl
  bool v3; // di
  bool v4; // r14
  char CurrentThreadId; // al
  int v6; // r8d
  int v7; // edx
  int v8; // r8d
  int v9; // r9d
  const char *v10; // r9
  bool v11; // di
  char v12; // al
  int v13; // r8d
  int v14; // edx
  __int64 result; // rax
  int v16; // [rsp+20h] [rbp-98h]
  int v17; // [rsp+20h] [rbp-98h]
  int v18; // [rsp+28h] [rbp-90h]
  int v19; // [rsp+28h] [rbp-90h]
  char *v20; // [rsp+30h] [rbp-88h]
  const char *v21; // [rsp+60h] [rbp-58h] BYREF
  const char *v22; // [rsp+68h] [rbp-50h] BYREF
  int v23[2]; // [rsp+70h] [rbp-48h] BYREF
  const char *v24; // [rsp+78h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  int v26; // [rsp+C0h] [rbp+8h] BYREF
  __int64 v27; // [rsp+C8h] [rbp+10h] BYREF
  const char *v28; // [rsp+D0h] [rbp+18h] BYREF
  int *v29; // [rsp+D8h] [rbp+20h] BYREF

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
      v16,
      v18,
      12,
      &WPP_ad6665f7b8be3bbcc1289583115d6a25_Traceguids,
      CurrentThreadId);
  }
  try
  {
    LOBYTE(v16) = *((_BYTE *)this + 168) == 0;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x5F,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvprocessor.cpp",
      (const char *)0x8000FFFFLL,
      v16,
      (bool)"Processor is not started",
      v20);
    if ( (unsigned int)dword_1800C1058 > 4
      && (qword_1800C1068 & 0x470000000000LL) != 0
      && (qword_1800C1070 & 0x470000000000LL) == qword_1800C1070 )
    {
      v27 = *((_QWORD *)this + 8);
      v26 = *((_DWORD *)this + 18);
      v28 = "Stop Yuv processor";
      v29 = &xmmword_1800C21A0;
      v21 = "DirectStreamMedia_Driver";
      v22 = "RdpAvenc";
      *(_QWORD *)v23 = 0x1000000;
      v24 = "Checkpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)qword_1800B3F18,
        v8,
        v9,
        (__int64)&v24,
        (__int64)v23,
        (__int64)&v22,
        (__int64)&v21,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v26,
        (__int64)&v27);
    }
    Rdp::Modern::Utils::CInflightRecorder::push0(
      (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      L"YuvProcessorStop",
      "Rdp::Avenc::Yuv::CYuvProcessor::Stop",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvprocessor.cpp",
      0x6Bu);
    *((_BYTE *)this + 168) = 0;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v2 = 0;
    }
    v11 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v12 = GetCurrentThreadId();
      LOBYTE(v13) = v11;
      LOBYTE(v14) = v2;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v14,
        v13,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v17,
        v19,
        13,
        &WPP_ad6665f7b8be3bbcc1289583115d6a25_Traceguids,
        v12);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x72,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvprocessor.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x18005c770  push    rbx
0x18005c772  push    rsi
0x18005c773  push    rdi
0x18005c774  push    r12
0x18005c776  push    r13
0x18005c778  push    r14
0x18005c77a  push    r15
0x18005c77c  sub     rsp, 80h
0x18005c783  mov     rsi, rcx
0x18005c786  lea     r12, WPP_GLOBAL_Control
0x18005c78d  mov     rax, cs:WPP_GLOBAL_Control
0x18005c794  mov     bl, 1
0x18005c796  cmp     rax, r12
0x18005c799  jz      short loc_18005C7AB
0x18005c79b  test    [rax+1Ch], bl
0x18005c79e  jz      short loc_18005C7AB
0x18005c7a0  cmp     byte ptr [rax+19h], 4
0x18005c7a4  jb      short loc_18005C7AB
0x18005c7a6  mov     dil, bl
0x18005c7a9  jmp     short loc_18005C7AE
0x18005c7ab  xor     dil, dil
0x18005c7ae  lea     r13, WPP_RECORDER_INITIALIZED
0x18005c7b5  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18005c7bc  setnz   r14b
0x18005c7c0  test    dil, dil
0x18005c7c3  jnz     short loc_18005C7D3
0x18005c7c5  test    r14b, r14b
0x18005c7c8  jnz     short loc_18005C7D3
0x18005c7ca  lea     r15, WPP_ad6665f7b8be3bbcc1289583115d6a25_Traceguids
0x18005c7d1  jmp     short loc_18005C80A
0x18005c7d3  call    cs:__imp_GetCurrentThreadId
0x18005c7d9  mov     dword ptr [rsp+0B8h+var_78], eax; char
0x18005c7dd  lea     r15, WPP_ad6665f7b8be3bbcc1289583115d6a25_Traceguids
0x18005c7e4  mov     [rsp+0B8h+MessageGuid], r15; MessageGuid
0x18005c7e9  mov     word ptr [rsp+0B8h+var_88], 0Ch; char *
0x18005c7f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c7f7  mov     r9, [rcx+28h]; int
0x18005c7fb  mov     r8b, r14b; int
0x18005c7fe  mov     dl, dil; int
0x18005c801  mov     rcx, [rcx+10h]; int
0x18005c805  call    WPP_RECORDER_AND_TRACE_SF_D
0x18005c80a  cmp     byte ptr [rsi+0A8h], 0
0x18005c811  setz    al
0x18005c814  mov     rcx, [rsp+0B8h]; this
0x18005c81c  lea     rdx, aProcessorIsNot; "Processor is not started"
0x18005c823  mov     qword ptr [rsp+0B8h+var_90], rdx; bool
0x18005c828  mov     byte ptr [rsp+0B8h+var_98], al; int
0x18005c82c  mov     r9d, 8000FFFFh; char *
0x18005c832  lea     r8, aOnecoreuapTerm_33; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18005c839  mov     edx, 5Fh ; '_'; void *
0x18005c83e  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18005c843  mov     eax, cs:dword_1800C1058
0x18005c849  cmp     eax, 4
0x18005c84c  jbe     loc_18005C952
0x18005c852  mov     rcx, cs:qword_1800C1070
0x18005c859  mov     rax, cs:qword_1800C1068
0x18005c860  mov     rdx, 470000000000h
0x18005c86a  test    rdx, rax
0x18005c86d  jz      loc_18005C952
0x18005c873  mov     rax, rcx
0x18005c876  and     rax, rdx
0x18005c879  cmp     rax, rcx
0x18005c87c  jnz     loc_18005C952
0x18005c882  mov     rax, [rsi+40h]
0x18005c886  mov     [rsp+0B8h+arg_8], rax
0x18005c88e  mov     eax, [rsi+48h]
0x18005c891  mov     [rsp+0B8h+arg_0], eax
0x18005c898  lea     rax, aStopYuvProcess; "Stop Yuv processor"
0x18005c89f  mov     [rsp+0B8h+arg_10], rax
0x18005c8a7  lea     rax, xmmword_1800C21A0
0x18005c8ae  mov     [rsp+0B8h+arg_18], rax
0x18005c8b6  lea     rax, aDirectstreamme_0; "DirectStreamMedia_Driver"
0x18005c8bd  mov     [rsp+0B8h+var_58], rax
0x18005c8c2  lea     rax, aRdpavenc; "RdpAvenc"
0x18005c8c9  mov     [rsp+0B8h+var_50], rax
0x18005c8ce  mov     qword ptr [rsp+0B8h+var_48], 1000000h
0x18005c8d7  lea     rax, aCheckpoint; "Checkpoint"
0x18005c8de  mov     [rsp+0B8h+var_40], rax
0x18005c8e3  lea     rax, [rsp+0B8h+arg_8]
0x18005c8eb  mov     [rsp+0B8h+var_60], rax
0x18005c8f0  lea     rax, [rsp+0B8h+arg_0]
0x18005c8f8  mov     [rsp+0B8h+var_68], rax
0x18005c8fd  lea     rax, [rsp+0B8h+arg_10]
0x18005c905  mov     [rsp+0B8h+var_70], rax
0x18005c90a  lea     rax, [rsp+0B8h+arg_18]
0x18005c912  mov     qword ptr [rsp+0B8h+var_78], rax
0x18005c917  lea     rax, [rsp+0B8h+var_58]
0x18005c91c  mov     [rsp+0B8h+MessageGuid], rax
0x18005c921  lea     rax, [rsp+0B8h+var_50]
0x18005c926  mov     [rsp+0B8h+var_88], rax
0x18005c92b  lea     rax, [rsp+0B8h+var_48]
0x18005c930  mov     qword ptr [rsp+0B8h+var_90], rax; int
0x18005c935  lea     rax, [rsp+0B8h+var_40]
0x18005c93a  mov     qword ptr [rsp+0B8h+var_98], rax
0x18005c93f  lea     rdx, qword_1800B3F18
0x18005c946  lea     rcx, dword_1800C1058
0x18005c94d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@33AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18005c952  mov     [rsp+0B8h+var_98], 6Bh ; 'k'; int
0x18005c95a  lea     r9, aOnecoreuapTerm_33; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18005c961  lea     r8, aRdpAvencYuvCyu_4; "Rdp::Avenc::Yuv::CYuvProcessor::Stop"
0x18005c968  lea     rdx, aYuvprocessorst_0; "YuvProcessorStop"
0x18005c96f  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18005c976  call    ?push0@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1I@Z; Rdp::Modern::Utils::CInflightRecorder::push0(ushort const *,char const *,char const *,uint)
0x18005c97b  mov     byte ptr [rsi+0A8h], 0
0x18005c982  mov     rax, cs:WPP_GLOBAL_Control
0x18005c989  cmp     rax, r12
0x18005c98c  jz      short loc_18005C999
0x18005c98e  test    [rax+1Ch], bl
0x18005c991  jz      short loc_18005C999
0x18005c993  cmp     byte ptr [rax+19h], 4
0x18005c997  jnb     short loc_18005C99B
0x18005c999  xor     bl, bl
0x18005c99b  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18005c9a2  setnz   dil
0x18005c9a6  test    bl, bl
0x18005c9a8  jnz     short loc_18005C9AF
0x18005c9aa  test    dil, dil
0x18005c9ad  jz      short loc_18005C9DE
0x18005c9af  call    cs:__imp_GetCurrentThreadId
0x18005c9b5  mov     dword ptr [rsp+0B8h+var_78], eax; char
0x18005c9b9  mov     [rsp+0B8h+MessageGuid], r15; MessageGuid
0x18005c9be  mov     word ptr [rsp+0B8h+var_88], 0Dh; __int16
0x18005c9c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c9cc  mov     r9, [rcx+28h]; int
0x18005c9d0  mov     r8b, dil; int
0x18005c9d3  mov     dl, bl; int
0x18005c9d5  mov     rcx, [rcx+10h]; int
0x18005c9d9  call    WPP_RECORDER_AND_TRACE_SF_D
0x18005c9de  xor     eax, eax
0x18005c9e0  jmp     short loc_18005C9E9
0x18005c9e2  mov     eax, [rsp+0B8h+arg_0]
0x18005c9e9  add     rsp, 80h
0x18005c9f0  pop     r15
0x18005c9f2  pop     r14
0x18005c9f4  pop     r13
0x18005c9f6  pop     r12
0x18005c9f8  pop     rdi
0x18005c9f9  pop     rsi
0x18005c9fa  pop     rbx
0x18005c9fb  retn
```
