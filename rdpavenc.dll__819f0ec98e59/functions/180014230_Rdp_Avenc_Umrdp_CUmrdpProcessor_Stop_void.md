# Rdp::Avenc::Umrdp::CUmrdpProcessor::Stop(void)

- ea: `0x180014230`
- end: `0x1800144cb`
- name: `?Stop@CUmrdpProcessor@Umrdp@Avenc@Rdp@@UEAAJXZ`
- size: `667`
- prototype: `__int64 __fastcall(Rdp::Avenc::Umrdp::CUmrdpProcessor *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800019f0`
- `0x18000b07c`
- `0x180014230`
- `0x1800146bc`
- `0x1800152c4`
- `0x180015480`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001442f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001442f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014293`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014472`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014293`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014472`

## pseudocode

```c
__int64 __fastcall Rdp::Avenc::Umrdp::CUmrdpProcessor::Stop(Rdp::Avenc::Umrdp::CUmrdpProcessor *this)
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
  __int64 v11; // rcx
  unsigned int v12; // r8d
  bool v13; // di
  char v14; // al
  int v15; // r8d
  int v16; // edx
  __int64 result; // rax
  int v18; // [rsp+20h] [rbp-98h]
  int v19; // [rsp+20h] [rbp-98h]
  int v20; // [rsp+28h] [rbp-90h]
  int v21; // [rsp+28h] [rbp-90h]
  char *v22; // [rsp+30h] [rbp-88h]
  const char *v23; // [rsp+60h] [rbp-58h] BYREF
  int v24[2]; // [rsp+68h] [rbp-50h] BYREF
  const char *v25; // [rsp+70h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  int v27; // [rsp+C0h] [rbp+8h] BYREF
  __int64 v28; // [rsp+C8h] [rbp+10h] BYREF
  const char *v29; // [rsp+D0h] [rbp+18h] BYREF
  int *v30; // [rsp+D8h] [rbp+20h] BYREF

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
      v18,
      v20,
      14,
      &WPP_44e245a864023212cc554d824265b257_Traceguids,
      CurrentThreadId);
  }
  try
  {
    LOBYTE(v18) = *((_BYTE *)this + 16) == 0;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0xCF,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\umrdpprocessor.cpp",
      (const char *)0x8000FFFFLL,
      v18,
      (bool)"Processor is not started",
      v22);
    if ( (unsigned int)dword_1800C1058 > 4
      && (qword_1800C1068 & 0x470000000000LL) != 0
      && (qword_1800C1070 & 0x470000000000LL) == qword_1800C1070 )
    {
      v28 = *(_QWORD *)((char *)this + 108);
      v27 = *((_DWORD *)this + 29);
      v29 = "Stop Umrdp processor";
      v30 = &xmmword_1800C21A0;
      v23 = "RdpAvenc";
      *(_QWORD *)v24 = 0x1000000;
      v25 = "Checkpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)qword_1800AC800,
        v8,
        v9,
        (__int64)&v25,
        (__int64)v24,
        (__int64)&v23,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v27,
        (__int64)&v28);
    }
    Rdp::Modern::Utils::CInflightRecorder::push0(
      (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      L"UmrdpProcessorStop",
      "Rdp::Avenc::Umrdp::CUmrdpProcessor::Stop",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\umrdpprocessor.cpp",
      0xDAu);
    v11 = *((_QWORD *)this + 7);
    if ( v11 && !SetEvent(*(HANDLE *)(v11 + 120)) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v12, v10);
    *((_BYTE *)this + 16) = 0;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v2 = 0;
    }
    v13 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v14 = GetCurrentThreadId();
      LOBYTE(v15) = v13;
      LOBYTE(v16) = v2;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v16,
        v15,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v19,
        v21,
        15,
        &WPP_44e245a864023212cc554d824265b257_Traceguids,
        v14);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xE9,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\umrdpprocessor.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x180014230  push    rbx
0x180014232  push    rsi
0x180014233  push    rdi
0x180014234  push    r12
0x180014236  push    r13
0x180014238  push    r14
0x18001423a  push    r15
0x18001423c  sub     rsp, 80h
0x180014243  mov     rsi, rcx
0x180014246  lea     r12, WPP_GLOBAL_Control
0x18001424d  mov     rax, cs:WPP_GLOBAL_Control
0x180014254  mov     bl, 1
0x180014256  cmp     rax, r12
0x180014259  jz      short loc_18001426B
0x18001425b  test    [rax+1Ch], bl
0x18001425e  jz      short loc_18001426B
0x180014260  cmp     byte ptr [rax+19h], 4
0x180014264  jb      short loc_18001426B
0x180014266  mov     dil, bl
0x180014269  jmp     short loc_18001426E
0x18001426b  xor     dil, dil
0x18001426e  lea     r13, WPP_RECORDER_INITIALIZED
0x180014275  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18001427c  setnz   r14b
0x180014280  test    dil, dil
0x180014283  jnz     short loc_180014293
0x180014285  test    r14b, r14b
0x180014288  jnz     short loc_180014293
0x18001428a  lea     r15, WPP_44e245a864023212cc554d824265b257_Traceguids
0x180014291  jmp     short loc_1800142CA
0x180014293  call    cs:__imp_GetCurrentThreadId
0x180014299  mov     dword ptr [rsp+0B8h+var_78], eax; char
0x18001429d  lea     r15, WPP_44e245a864023212cc554d824265b257_Traceguids
0x1800142a4  mov     [rsp+0B8h+MessageGuid], r15; MessageGuid
0x1800142a9  mov     word ptr [rsp+0B8h+var_88], 0Eh; char *
0x1800142b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800142b7  mov     r9, [rcx+28h]; int
0x1800142bb  mov     r8b, r14b; int
0x1800142be  mov     dl, dil; int
0x1800142c1  mov     rcx, [rcx+10h]; int
0x1800142c5  call    WPP_RECORDER_AND_TRACE_SF_D
0x1800142ca  cmp     byte ptr [rsi+10h], 0
0x1800142ce  setz    al
0x1800142d1  mov     rcx, [rsp+0B8h]; this
0x1800142d9  lea     rdx, aProcessorIsNot; "Processor is not started"
0x1800142e0  mov     qword ptr [rsp+0B8h+var_90], rdx; bool
0x1800142e5  mov     byte ptr [rsp+0B8h+var_98], al; int
0x1800142e9  mov     r9d, 8000FFFFh; char *
0x1800142ef  lea     r8, aOnecoreuapTerm_58; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x1800142f6  mov     edx, 0CFh; void *
0x1800142fb  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180014300  mov     eax, cs:dword_1800C1058
0x180014306  cmp     eax, 4
0x180014309  jbe     loc_1800143F9
0x18001430f  mov     rcx, cs:qword_1800C1070
0x180014316  mov     rax, cs:qword_1800C1068
0x18001431d  mov     rdx, 470000000000h
0x180014327  test    rdx, rax
0x18001432a  jz      loc_1800143F9
0x180014330  mov     rax, rcx
0x180014333  and     rax, rdx
0x180014336  cmp     rax, rcx
0x180014339  jnz     loc_1800143F9
0x18001433f  mov     rax, [rsi+6Ch]
0x180014343  mov     [rsp+0B8h+arg_8], rax
0x18001434b  mov     eax, [rsi+74h]
0x18001434e  mov     [rsp+0B8h+arg_0], eax
0x180014355  lea     rax, aStopUmrdpProce; "Stop Umrdp processor"
0x18001435c  mov     [rsp+0B8h+arg_10], rax
0x180014364  lea     rax, xmmword_1800C21A0
0x18001436b  mov     [rsp+0B8h+arg_18], rax
0x180014373  lea     rax, aRdpavenc; "RdpAvenc"
0x18001437a  mov     [rsp+0B8h+var_58], rax
0x18001437f  mov     qword ptr [rsp+0B8h+var_50], 1000000h
0x180014388  lea     rax, aCheckpoint; "Checkpoint"
0x18001438f  mov     [rsp+0B8h+var_48], rax
0x180014394  lea     rax, [rsp+0B8h+arg_8]
0x18001439c  mov     [rsp+0B8h+var_68], rax
0x1800143a1  lea     rax, [rsp+0B8h+arg_0]
0x1800143a9  mov     [rsp+0B8h+var_70], rax
0x1800143ae  lea     rax, [rsp+0B8h+arg_10]
0x1800143b6  mov     qword ptr [rsp+0B8h+var_78], rax
0x1800143bb  lea     rax, [rsp+0B8h+arg_18]
0x1800143c3  mov     [rsp+0B8h+MessageGuid], rax
0x1800143c8  lea     rax, [rsp+0B8h+var_58]
0x1800143cd  mov     [rsp+0B8h+var_88], rax
0x1800143d2  lea     rax, [rsp+0B8h+var_50]
0x1800143d7  mov     qword ptr [rsp+0B8h+var_90], rax; int
0x1800143dc  lea     rax, [rsp+0B8h+var_48]
0x1800143e1  mov     qword ptr [rsp+0B8h+var_98], rax
0x1800143e6  lea     rdx, qword_1800AC800
0x1800143ed  lea     rcx, dword_1800C1058
0x1800143f4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1800143f9  mov     [rsp+0B8h+var_98], 0DAh; int
0x180014401  lea     r9, aOnecoreuapTerm_58; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180014408  lea     r8, aRdpAvencUmrdpC_3; "Rdp::Avenc::Umrdp::CUmrdpProcessor::Sto"...
0x18001440f  lea     rdx, aUmrdpprocessor; "UmrdpProcessorStop"
0x180014416  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18001441d  call    ?push0@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1I@Z; Rdp::Modern::Utils::CInflightRecorder::push0(ushort const *,char const *,char const *,uint)
0x180014422  mov     rcx, [rsi+38h]
0x180014426  test    rcx, rcx
0x180014429  jz      short loc_180014441
0x18001442b  mov     rcx, [rcx+78h]; hEvent
0x18001442f  call    cs:__imp_SetEvent
0x180014435  mov     rcx, [rsp+0B8h]; this
0x18001443d  test    eax, eax
0x18001443f  jz      short loc_1800144BF
0x180014441  mov     byte ptr [rsi+10h], 0
0x180014445  mov     rax, cs:WPP_GLOBAL_Control
0x18001444c  cmp     rax, r12
0x18001444f  jz      short loc_18001445C
0x180014451  test    [rax+1Ch], bl
0x180014454  jz      short loc_18001445C
0x180014456  cmp     byte ptr [rax+19h], 4
0x18001445a  jnb     short loc_18001445E
0x18001445c  xor     bl, bl
0x18001445e  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180014465  setnz   dil
0x180014469  test    bl, bl
0x18001446b  jnz     short loc_180014472
0x18001446d  test    dil, dil
0x180014470  jz      short loc_1800144A1
0x180014472  call    cs:__imp_GetCurrentThreadId
0x180014478  mov     dword ptr [rsp+0B8h+var_78], eax; char
0x18001447c  mov     [rsp+0B8h+MessageGuid], r15; MessageGuid
0x180014481  mov     word ptr [rsp+0B8h+var_88], 0Fh; __int16
0x180014488  mov     rcx, cs:WPP_GLOBAL_Control
0x18001448f  mov     r9, [rcx+28h]; int
0x180014493  mov     r8b, dil; int
0x180014496  mov     dl, bl; int
0x180014498  mov     rcx, [rcx+10h]; int
0x18001449c  call    WPP_RECORDER_AND_TRACE_SF_D
0x1800144a1  xor     eax, eax
0x1800144a3  jmp     short loc_1800144AC
0x1800144a5  mov     eax, [rsp+0B8h+arg_0]
0x1800144ac  add     rsp, 80h
0x1800144b3  pop     r15
0x1800144b5  pop     r14
0x1800144b7  pop     r13
0x1800144b9  pop     r12
0x1800144bb  pop     rdi
0x1800144bc  pop     rsi
0x1800144bd  pop     rbx
0x1800144be  retn
0x1800144bf  mov     edx, 0A01h; void *
0x1800144c4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
