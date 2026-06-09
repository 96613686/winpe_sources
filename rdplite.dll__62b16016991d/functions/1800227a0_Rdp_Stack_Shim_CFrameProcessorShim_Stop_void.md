# Rdp::Stack::Shim::CFrameProcessorShim::Stop(void)

- ea: `0x1800227a0`
- end: `0x1800229f9`
- name: `?Stop@CFrameProcessorShim@Shim@Stack@Rdp@@QEAAXXZ`
- size: `601`
- prototype: `void __fastcall(Rdp::Stack::Shim::CFrameProcessorShim *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x18001ec84`
- `0x18001ef38`

## callees

- `0x18000141c`
- `0x180001574`
- `0x18000b1bc`
- `0x18000cea4`
- `0x18000d858`
- `0x18000dbf4`
- `0x1800227a0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022802`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800229b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022802`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800229b9`

## pseudocode

```c
void __fastcall Rdp::Stack::Shim::CFrameProcessorShim::Stop(Rdp::Stack::Shim::CFrameProcessorShim *this)
{
  char v2; // bl
  bool v3; // di
  bool v4; // si
  char CurrentThreadId; // al
  int v6; // r8d
  int v7; // edx
  int v8; // r8d
  int v9; // r9d
  unsigned int v10; // eax
  bool v11; // di
  char v12; // al
  int v13; // r8d
  int v14; // edx
  int v15; // [rsp+20h] [rbp-48h]
  int v16; // [rsp+20h] [rbp-48h]
  int v17; // [rsp+28h] [rbp-40h]
  char *v18; // [rsp+28h] [rbp-40h]
  int v19; // [rsp+28h] [rbp-40h]
  char *v20; // [rsp+30h] [rbp-38h]
  char v21[8]; // [rsp+50h] [rbp-18h] BYREF
  const char *v22; // [rsp+58h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]
  int v24; // [rsp+B0h] [rbp+48h] BYREF
  const char *v25; // [rsp+B8h] [rbp+50h] BYREF
  __int128 *v26; // [rsp+C0h] [rbp+58h] BYREF
  const char *v27; // [rsp+C8h] [rbp+60h] BYREF

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
      v15,
      v17,
      12,
      &WPP_8b5be1e1131037f88503b0e25167cb2c_Traceguids,
      CurrentThreadId);
  }
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x6A,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\frameprocessorshim.cpp",
    (const char *)0x8000FFFFLL,
    *((_BYTE *)this + 312) == 0,
    (bool)"Frame processor shim is not started",
    v20);
  if ( (unsigned int)dword_18003C058 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18003C058, 0x470000000000LL) )
  {
    v24 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 37) + 232LL) + 336LL);
    v25 = "Stop frame processor shim";
    v26 = &xmmword_18003CA50;
    v27 = "RdpLite";
    v22 = "Checkpoint";
    *(_QWORD *)v21 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_18003C058,
      (unsigned int)&unk_180036338,
      v8,
      v9,
      (__int64)&v22,
      (__int64)v21,
      (__int64)&v27,
      (__int64)&v26,
      (__int64)&v25,
      (__int64)&v24);
  }
  Rdp::Modern::Utils::CInflightRecorder::push0(
    (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
    L"FrameProcessorShimStop",
    "Rdp::Stack::Shim::CFrameProcessorShim::Stop",
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\frameprocessorshim.cpp",
    0x74u);
  v10 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 38) + 40LL))(*((_QWORD *)this + 38));
  wil::details::in1diag3::Log_IfFailedMsg(
    retaddr,
    (void *)0x7A,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\frameprocessorshim.cpp",
    (const char *)v10,
    (int)"Failed to stop frame processor",
    v18);
  *((_BYTE *)this + 312) = 0;
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
      v16,
      v19,
      13,
      &WPP_8b5be1e1131037f88503b0e25167cb2c_Traceguids,
      v12);
  }
}

```

## disassembly

```asm
0x1800227a0  push    rbp
0x1800227a2  push    rbx
0x1800227a3  push    rsi
0x1800227a4  push    rdi
0x1800227a5  push    r12
0x1800227a7  push    r13
0x1800227a9  push    r14
0x1800227ab  push    r15
0x1800227ad  mov     rbp, rsp
0x1800227b0  sub     rsp, 68h
0x1800227b4  mov     r14, rcx
0x1800227b7  mov     rax, cs:WPP_GLOBAL_Control
0x1800227be  lea     r13, WPP_GLOBAL_Control
0x1800227c5  mov     bl, 1
0x1800227c7  cmp     rax, r13
0x1800227ca  jz      short loc_1800227DC
0x1800227cc  test    [rax+1Ch], bl
0x1800227cf  jz      short loc_1800227DC
0x1800227d1  cmp     byte ptr [rax+19h], 4
0x1800227d5  jb      short loc_1800227DC
0x1800227d7  mov     dil, bl
0x1800227da  jmp     short loc_1800227DF
0x1800227dc  xor     dil, dil
0x1800227df  lea     r15, WPP_RECORDER_INITIALIZED
0x1800227e6  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1800227ed  lea     r12, WPP_8b5be1e1131037f88503b0e25167cb2c_Traceguids
0x1800227f4  setnz   sil
0x1800227f8  test    dil, dil
0x1800227fb  jnz     short loc_180022802
0x1800227fd  test    sil, sil
0x180022800  jz      short loc_180022832
0x180022802  call    cs:__imp_GetCurrentThreadId
0x180022808  mov     rcx, cs:WPP_GLOBAL_Control
0x18002280f  mov     r8b, sil; int
0x180022812  mov     dword ptr [rsp+68h+var_28], eax; char
0x180022816  mov     dl, dil; int
0x180022819  mov     [rsp+68h+MessageGuid], r12; MessageGuid
0x18002281e  mov     word ptr [rsp+68h+var_38], 0Ch; char *
0x180022825  mov     r9, [rcx+28h]; int
0x180022829  mov     rcx, [rcx+10h]; int
0x18002282d  call    WPP_RECORDER_AND_TRACE_SF_D
0x180022832  cmp     byte ptr [r14+138h], 0
0x18002283a  lea     rdx, aFrameProcessor; "Frame processor shim is not started"
0x180022841  mov     rcx, [rbp+40h]; this
0x180022845  lea     rdi, aOnecoreuapTerm_1; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18002284c  mov     [rsp+68h+var_40], rdx; bool
0x180022851  setz    al
0x180022854  mov     r9d, 8000FFFFh; char *
0x18002285a  mov     [rsp+68h+var_48], al; char
0x18002285e  mov     r8, rdi; unsigned int
0x180022861  mov     edx, 6Ah ; 'j'; void *
0x180022866  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18002286b  mov     eax, cs:dword_18003C058
0x180022871  cmp     eax, 4
0x180022874  jbe     loc_18002292C
0x18002287a  mov     rdx, 470000000000h
0x180022884  lea     rcx, dword_18003C058
0x18002288b  call    _tlgKeywordOn
0x180022890  test    al, al
0x180022892  jz      loc_18002292C
0x180022898  mov     rax, [r14+128h]
0x18002289f  lea     rdx, unk_180036338
0x1800228a6  mov     rcx, [rax+0E8h]
0x1800228ad  mov     eax, [rcx+150h]
0x1800228b3  lea     rcx, dword_18003C058
0x1800228ba  mov     [rbp+arg_0], eax
0x1800228bd  lea     rax, aStopFrameProce; "Stop frame processor shim"
0x1800228c4  mov     [rbp+arg_8], rax
0x1800228c8  lea     rax, xmmword_18003CA50
0x1800228cf  mov     [rbp+arg_10], rax
0x1800228d3  lea     rax, aRdplite; "RdpLite"
0x1800228da  mov     [rbp+arg_18], rax
0x1800228de  lea     rax, aCheckpoint; "Checkpoint"
0x1800228e5  mov     [rbp+var_10], rax
0x1800228e9  lea     rax, [rbp+arg_0]
0x1800228ed  mov     [rsp+68h+var_20], rax
0x1800228f2  lea     rax, [rbp+arg_8]
0x1800228f6  mov     qword ptr [rsp+68h+var_28], rax
0x1800228fb  lea     rax, [rbp+arg_10]
0x1800228ff  mov     [rsp+68h+MessageGuid], rax
0x180022904  lea     rax, [rbp+arg_18]
0x180022908  mov     [rsp+68h+var_38], rax
0x18002290d  lea     rax, [rbp+var_18]
0x180022911  mov     [rsp+68h+var_40], rax; int
0x180022916  lea     rax, [rbp+var_10]
0x18002291a  mov     qword ptr [rsp+68h+var_48], rax
0x18002291f  mov     qword ptr [rbp+var_18], 1000000h
0x180022927  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18002292c  mov     r9, rdi; char *
0x18002292f  mov     dword ptr [rsp+68h+var_48], 74h ; 't'; unsigned int
0x180022937  lea     r8, aRdpStackShimCf_2; "Rdp::Stack::Shim::CFrameProcessorShim::"...
0x18002293e  lea     rdx, aFrameprocessor_0; "FrameProcessorShimStop"
0x180022945  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18002294c  call    ?push0@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1I@Z; Rdp::Modern::Utils::CInflightRecorder::push0(ushort const *,char const *,char const *,uint)
0x180022951  mov     rcx, [r14+130h]
0x180022958  mov     rax, [rcx]
0x18002295b  mov     rax, [rax+28h]
0x18002295f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022964  mov     rcx, [rbp+40h]; this
0x180022968  lea     rdx, aFailedToStopFr; "Failed to stop frame processor"
0x18002296f  mov     qword ptr [rsp+68h+var_48], rdx; int
0x180022974  mov     r9d, eax; char *
0x180022977  mov     edx, 7Ah ; 'z'; void *
0x18002297c  mov     r8, rdi; unsigned int
0x18002297f  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180022984  mov     byte ptr [r14+138h], 0
0x18002298c  mov     rax, cs:WPP_GLOBAL_Control
0x180022993  cmp     rax, r13
0x180022996  jz      short loc_1800229A3
0x180022998  test    [rax+1Ch], bl
0x18002299b  jz      short loc_1800229A3
0x18002299d  cmp     byte ptr [rax+19h], 4
0x1800229a1  jnb     short loc_1800229A5
0x1800229a3  xor     bl, bl
0x1800229a5  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1800229ac  setnz   dil
0x1800229b0  test    bl, bl
0x1800229b2  jnz     short loc_1800229B9
0x1800229b4  test    dil, dil
0x1800229b7  jz      short loc_1800229E8
0x1800229b9  call    cs:__imp_GetCurrentThreadId
0x1800229bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800229c6  mov     r8b, dil; int
0x1800229c9  mov     dword ptr [rsp+68h+var_28], eax; char
0x1800229cd  mov     dl, bl; int
0x1800229cf  mov     [rsp+68h+MessageGuid], r12; MessageGuid
0x1800229d4  mov     word ptr [rsp+68h+var_38], 0Dh; __int16
0x1800229db  mov     r9, [rcx+28h]; int
0x1800229df  mov     rcx, [rcx+10h]; int
0x1800229e3  call    WPP_RECORDER_AND_TRACE_SF_D
0x1800229e8  add     rsp, 68h
0x1800229ec  pop     r15
0x1800229ee  pop     r14
0x1800229f0  pop     r13
0x1800229f2  pop     r12
0x1800229f4  pop     rdi
0x1800229f5  pop     rsi
0x1800229f6  pop     rbx
0x1800229f7  pop     rbp
0x1800229f8  retn
```
