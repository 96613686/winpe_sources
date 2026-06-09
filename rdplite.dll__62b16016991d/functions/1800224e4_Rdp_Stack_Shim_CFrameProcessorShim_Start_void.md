# Rdp::Stack::Shim::CFrameProcessorShim::Start(void)

- ea: `0x1800224e4`
- end: `0x180022798`
- name: `?Start@CFrameProcessorShim@Shim@Stack@Rdp@@QEAAXXZ`
- size: `692`
- prototype: `void __fastcall(Rdp::Stack::Shim::CFrameProcessorShim *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ce84`

## callees

- `0x18000141c`
- `0x180001574`
- `0x180007b28`
- `0x18000cf28`
- `0x18000d858`
- `0x18000dbf4`
- `0x1800210ec`
- `0x1800211dc`
- `0x1800224e4`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002254e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002275a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002254e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002275a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Rdp::Stack::Shim::CFrameProcessorShim::Start(Rdp::Stack::Shim::CFrameProcessorShim *this)
{
  char v2; // bl
  bool v3; // di
  bool v4; // r14
  char CurrentThreadId; // al
  int v6; // r8d
  int v7; // edx
  int v8; // r8d
  int v9; // r9d
  __int64 *v10; // rcx
  char v11; // di
  __int64 v12; // rax
  __int64 v13; // rcx
  unsigned int v14; // eax
  bool v15; // di
  char v16; // al
  int v17; // r8d
  int v18; // edx
  int v19; // [rsp+20h] [rbp-50h]
  int v20; // [rsp+20h] [rbp-50h]
  char *v21; // [rsp+28h] [rbp-48h]
  int v22; // [rsp+28h] [rbp-48h]
  const char *v23; // [rsp+50h] [rbp-20h] BYREF
  char v24[8]; // [rsp+58h] [rbp-18h] BYREF
  const char *v25; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  int v27; // [rsp+B8h] [rbp+48h] BYREF
  const char *v28; // [rsp+C0h] [rbp+50h] BYREF
  __int128 *v29; // [rsp+C8h] [rbp+58h] BYREF

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
      v19,
      (int)v21,
      10,
      &WPP_8b5be1e1131037f88503b0e25167cb2c_Traceguids,
      CurrentThreadId);
  }
  if ( (unsigned int)dword_18003C058 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18003C058, 0x470000000000LL) )
  {
    v27 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 37) + 232LL) + 336LL);
    v28 = "Start frame processor shim";
    v29 = &xmmword_18003CA50;
    v23 = "RdpLite";
    *(_QWORD *)v24 = 0x1000000;
    v25 = "Checkpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_18003C058,
      (unsigned int)&word_18003639E,
      v8,
      v9,
      (__int64)&v25,
      (__int64)v24,
      (__int64)&v23,
      (__int64)&v29,
      (__int64)&v28,
      (__int64)&v27);
  }
  Rdp::Modern::Utils::CInflightRecorder::push0(
    (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
    L"FrameProcessorShimStart",
    "Rdp::Stack::Shim::CFrameProcessorShim::Start",
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\frameprocessorshim.cpp",
    0x3Du);
  if ( *((_BYTE *)this + 313) )
  {
    v10 = (__int64 *)Rdp::Stack::Shim::CFrameProcessorShim::InternalCreateGpuFrameProcessor(this, &v28);
    v11 = 1;
  }
  else
  {
    v10 = (__int64 *)Rdp::Stack::Shim::CFrameProcessorShim::InternalCreateCpuFrameProcessor(this, &v27);
    v11 = 2;
  }
  v12 = *v10;
  *v10 = 0;
  v13 = *((_QWORD *)this + 38);
  *((_QWORD *)this + 38) = v12;
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  if ( (v11 & 2) != 0 )
  {
    v11 &= ~2u;
    wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&v27);
  }
  if ( (v11 & 1) != 0 )
    wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&v28);
  v14 = (*(__int64 (__fastcall **)(_QWORD, Rdp::Stack::Shim::CFrameProcessorShim *))(**((_QWORD **)this + 38) + 64LL))(
          *((_QWORD *)this + 38),
          this);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x4C,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\frameprocessorshim.cpp",
    (const char *)v14,
    (int)"Failed to start frame processor",
    v21);
  *((_BYTE *)this + 312) = 1;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
  {
    v2 = 0;
  }
  v15 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v16 = GetCurrentThreadId();
    LOBYTE(v17) = v15;
    LOBYTE(v18) = v2;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v18,
      v17,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v20,
      v22,
      11,
      &WPP_8b5be1e1131037f88503b0e25167cb2c_Traceguids,
      v16);
  }
}

```

## disassembly

```asm
0x1800224e4  push    rbp
0x1800224e6  push    rbx
0x1800224e7  push    rsi
0x1800224e8  push    rdi
0x1800224e9  push    r12
0x1800224eb  push    r13
0x1800224ed  push    r14
0x1800224ef  mov     rbp, rsp
0x1800224f2  sub     rsp, 70h
0x1800224f6  mov     rsi, rcx
0x1800224f9  mov     [rbp+arg_0], 0
0x180022500  lea     rcx, WPP_GLOBAL_Control
0x180022507  mov     ebx, 1
0x18002250c  mov     rax, cs:WPP_GLOBAL_Control
0x180022513  cmp     rax, rcx
0x180022516  jz      short loc_180022528
0x180022518  test    [rax+1Ch], bl
0x18002251b  jz      short loc_180022528
0x18002251d  cmp     byte ptr [rax+19h], 4
0x180022521  jb      short loc_180022528
0x180022523  mov     dil, bl
0x180022526  jmp     short loc_18002252B
0x180022528  xor     dil, dil
0x18002252b  lea     r12, WPP_RECORDER_INITIALIZED
0x180022532  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180022539  setnz   r14b
0x18002253d  lea     r13, WPP_8b5be1e1131037f88503b0e25167cb2c_Traceguids
0x180022544  test    dil, dil
0x180022547  jnz     short loc_18002254E
0x180022549  test    r14b, r14b
0x18002254c  jz      short loc_18002257E
0x18002254e  call    cs:__imp_GetCurrentThreadId
0x180022554  mov     dword ptr [rsp+70h+var_30], eax; char
0x180022558  mov     [rsp+70h+MessageGuid], r13; MessageGuid
0x18002255d  mov     [rsp+70h+var_40], 0Ah; __int16
0x180022564  mov     rcx, cs:WPP_GLOBAL_Control
0x18002256b  mov     r9, [rcx+28h]; int
0x18002256f  mov     r8b, r14b; int
0x180022572  mov     dl, dil; int
0x180022575  mov     rcx, [rcx+10h]; int
0x180022579  call    WPP_RECORDER_AND_TRACE_SF_D
0x18002257e  mov     eax, cs:dword_18003C058
0x180022584  cmp     eax, 4
0x180022587  jbe     loc_18002263F
0x18002258d  mov     rdx, 470000000000h
0x180022597  lea     rcx, dword_18003C058
0x18002259e  call    _tlgKeywordOn
0x1800225a3  test    al, al
0x1800225a5  jz      loc_18002263F
0x1800225ab  mov     rax, [rsi+128h]
0x1800225b2  mov     rcx, [rax+0E8h]
0x1800225b9  mov     eax, [rcx+150h]
0x1800225bf  mov     [rbp+arg_8], eax
0x1800225c2  lea     rax, aStartFrameProc; "Start frame processor shim"
0x1800225c9  mov     [rbp+arg_10], rax
0x1800225cd  lea     rax, xmmword_18003CA50
0x1800225d4  mov     [rbp+arg_18], rax
0x1800225d8  lea     rax, aRdplite; "RdpLite"
0x1800225df  mov     [rbp+var_20], rax
0x1800225e3  mov     qword ptr [rbp+var_18], 1000000h
0x1800225eb  lea     rax, aCheckpoint; "Checkpoint"
0x1800225f2  mov     [rbp+var_10], rax
0x1800225f6  lea     rax, [rbp+arg_8]
0x1800225fa  mov     [rsp+70h+var_28], rax
0x1800225ff  lea     rax, [rbp+arg_10]
0x180022603  mov     qword ptr [rsp+70h+var_30], rax
0x180022608  lea     rax, [rbp+arg_18]
0x18002260c  mov     [rsp+70h+MessageGuid], rax
0x180022611  lea     rax, [rbp+var_20]
0x180022615  mov     qword ptr [rsp+70h+var_40], rax
0x18002261a  lea     rax, [rbp+var_18]
0x18002261e  mov     [rsp+70h+var_48], rax; int
0x180022623  lea     rax, [rbp+var_10]
0x180022627  mov     qword ptr [rsp+70h+var_50], rax
0x18002262c  lea     rdx, word_18003639E
0x180022633  lea     rcx, dword_18003C058
0x18002263a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18002263f  mov     [rsp+70h+var_50], 3Dh ; '='; unsigned int
0x180022647  lea     r9, aOnecoreuapTerm_1; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18002264e  lea     r8, aRdpStackShimCf_1; "Rdp::Stack::Shim::CFrameProcessorShim::"...
0x180022655  lea     rdx, aFrameprocessor; "FrameProcessorShimStart"
0x18002265c  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x180022663  call    ?push0@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1I@Z; Rdp::Modern::Utils::CInflightRecorder::push0(ushort const *,char const *,char const *,uint)
0x180022668  mov     rcx, rsi
0x18002266b  cmp     byte ptr [rsi+139h], 0
0x180022672  jz      short loc_180022687
0x180022674  lea     rdx, [rbp+arg_10]
0x180022678  call    ?InternalCreateGpuFrameProcessor@CFrameProcessorShim@Shim@Stack@Rdp@@AEAA?AV?$com_ptr_t@UIFrameProcessor1@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@XZ; Rdp::Stack::Shim::CFrameProcessorShim::InternalCreateGpuFrameProcessor(void)
0x18002267d  mov     rcx, rax
0x180022680  mov     edi, ebx
0x180022682  mov     [rbp+arg_0], ebx
0x180022685  jmp     short loc_18002269B
0x180022687  lea     rdx, [rbp+arg_8]
0x18002268b  call    ?InternalCreateCpuFrameProcessor@CFrameProcessorShim@Shim@Stack@Rdp@@AEAA?AV?$com_ptr_t@UIFrameProcessor1@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@XZ; Rdp::Stack::Shim::CFrameProcessorShim::InternalCreateCpuFrameProcessor(void)
0x180022690  mov     rcx, rax
0x180022693  mov     edi, 2
0x180022698  mov     [rbp+arg_0], edi
0x18002269b  mov     rax, [rcx]
0x18002269e  mov     qword ptr [rcx], 0
0x1800226a5  mov     rcx, [rsi+130h]
0x1800226ac  mov     [rsi+130h], rax
0x1800226b3  test    rcx, rcx
0x1800226b6  jz      short loc_1800226C5
0x1800226b8  mov     rax, [rcx]
0x1800226bb  mov     rax, [rax+10h]
0x1800226bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800226c4  nop
0x1800226c5  test    dil, 2
0x1800226c9  jz      short loc_1800226D8
0x1800226cb  and     edi, 0FFFFFFFDh
0x1800226ce  lea     rcx, [rbp+arg_8]
0x1800226d2  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x1800226d7  nop
0x1800226d8  test    bl, dil
0x1800226db  jz      short loc_1800226E6
0x1800226dd  lea     rcx, [rbp+arg_10]
0x1800226e1  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x1800226e6  mov     rcx, [rsi+130h]
0x1800226ed  mov     rax, [rcx]
0x1800226f0  mov     rdx, rsi
0x1800226f3  mov     rax, [rax+40h]
0x1800226f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800226fc  mov     rcx, [rbp+38h]; this
0x180022700  lea     rdx, aFailedToStartF; "Failed to start frame processor"
0x180022707  mov     qword ptr [rsp+70h+var_50], rdx; int
0x18002270c  mov     r9d, eax; char *
0x18002270f  lea     r8, aOnecoreuapTerm_1; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180022716  mov     edx, 4Ch ; 'L'; void *
0x18002271b  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180022720  mov     [rsi+138h], bl
0x180022726  mov     rax, cs:WPP_GLOBAL_Control
0x18002272d  lea     rcx, WPP_GLOBAL_Control
0x180022734  cmp     rax, rcx
0x180022737  jz      short loc_180022744
0x180022739  test    [rax+1Ch], bl
0x18002273c  jz      short loc_180022744
0x18002273e  cmp     byte ptr [rax+19h], 4
0x180022742  jnb     short loc_180022746
0x180022744  xor     bl, bl
0x180022746  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18002274d  setnz   dil
0x180022751  test    bl, bl
0x180022753  jnz     short loc_18002275A
0x180022755  test    dil, dil
0x180022758  jz      short loc_180022789
0x18002275a  call    cs:__imp_GetCurrentThreadId
0x180022760  mov     dword ptr [rsp+70h+var_30], eax; char
0x180022764  mov     [rsp+70h+MessageGuid], r13; MessageGuid
0x180022769  mov     [rsp+70h+var_40], 0Bh; __int16
0x180022770  mov     rcx, cs:WPP_GLOBAL_Control
0x180022777  mov     r9, [rcx+28h]; int
0x18002277b  mov     r8b, dil; int
0x18002277e  mov     dl, bl; int
0x180022780  mov     rcx, [rcx+10h]; int
0x180022784  call    WPP_RECORDER_AND_TRACE_SF_D
0x180022789  add     rsp, 70h
0x18002278d  pop     r14
0x18002278f  pop     r13
0x180022791  pop     r12
0x180022793  pop     rdi
0x180022794  pop     rsi
0x180022795  pop     rbx
0x180022796  pop     rbp
0x180022797  retn
```
