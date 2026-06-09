# Rdp::Avenc::Umrdp::CFrameProcessor<Rdp::Avenc::IGpuFrameProcessor>::Stop(void)

- ea: `0x18001ed10`
- end: `0x18001ef89`
- name: `?Stop@?$CFrameProcessor@UIGpuFrameProcessor@Avenc@Rdp@@@Umrdp@Avenc@Rdp@@UEAAJXZ`
- size: `633`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001c78`
- `0x1800153f8`
- `0x180015480`
- `0x18001d494`
- `0x18001ed10`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ed73`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ef3b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ed73`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ef3b`

## pseudocode

```c
__int64 __fastcall Rdp::Avenc::Umrdp::CFrameProcessor<Rdp::Avenc::IGpuFrameProcessor>::Stop(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4)
{
  char v5; // bl
  bool v6; // di
  bool v7; // r14
  char CurrentThreadId; // al
  int v9; // r8d
  int v10; // edx
  __int64 v11; // rcx
  __int64 v12; // rcx
  bool v13; // di
  char v14; // al
  int v15; // r8d
  int v16; // edx
  int v18; // [rsp+20h] [rbp-98h]
  int v19; // [rsp+20h] [rbp-98h]
  int v20; // [rsp+28h] [rbp-90h]
  int v21; // [rsp+28h] [rbp-90h]
  const char *v22; // [rsp+60h] [rbp-58h] BYREF
  __int64 v23; // [rsp+68h] [rbp-50h] BYREF
  const char *v24; // [rsp+70h] [rbp-48h] BYREF
  int v25; // [rsp+C0h] [rbp+8h] BYREF
  int v26; // [rsp+C8h] [rbp+10h] BYREF
  const char *v27; // [rsp+D0h] [rbp+18h] BYREF
  int *v28; // [rsp+D8h] [rbp+20h] BYREF

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
      v18,
      v20,
      10,
      &WPP_19b31c027c473e795a0f5fbb7cb41a6c_Traceguids,
      CurrentThreadId);
  }
  if ( (unsigned int)dword_1800C1058 > 4
    && (qword_1800C1068 & 0x470000000000LL) != 0
    && (qword_1800C1070 & 0x470000000000LL) == qword_1800C1070 )
  {
    v11 = *(_QWORD *)(a1 + 24);
    v25 = *(_DWORD *)(v11 + 128);
    v26 = *(_DWORD *)(*(_QWORD *)(v11 + 120) + 196LL);
    v27 = "Stop Umrdp frame processor";
    v28 = &xmmword_1800C21A0;
    v22 = "RdpAvenc";
    v23 = 0x1000000;
    v24 = "Checkpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_1800C1058,
      (unsigned int)byte_1800AD033,
      a3,
      a4,
      (__int64)&v24,
      (__int64)&v23,
      (__int64)&v22,
      (__int64)&v28,
      (__int64)&v27,
      (__int64)&v26,
      (__int64)&v25);
  }
  v21 = *(_DWORD *)(*(_QWORD *)(a1 + 24) + 128LL);
  Rdp::Modern::Utils::CInflightRecorder::pushN(
    (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
    (wchar_t *)L"UmrdpFrameProcessorStop: Id %d",
    "Rdp::Avenc::Umrdp::CFrameProcessor<struct Rdp::Avenc::IGpuFrameProcessor>::Stop",
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\frameprocessor.cpp",
    0x4Au);
  Rdp::Avenc::Umrdp::CFrameProcessor<Rdp::Avenc::IGpuFrameProcessor>::DestroyRdpSurface(a1 - 80);
  v12 = *(_QWORD *)(a1 + 24);
  *(_QWORD *)(a1 + 24) = 0;
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
  {
    v5 = 0;
  }
  v13 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v14 = GetCurrentThreadId();
    LOBYTE(v15) = v13;
    LOBYTE(v16) = v5;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v16,
      v15,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v19,
      v21,
      11,
      &WPP_19b31c027c473e795a0f5fbb7cb41a6c_Traceguids,
      v14);
  }
  return 0;
}

```

## disassembly

```asm
0x18001ed10  push    rbx
0x18001ed12  push    rsi
0x18001ed13  push    rdi
0x18001ed14  push    r12
0x18001ed16  push    r13
0x18001ed18  push    r14
0x18001ed1a  push    r15
0x18001ed1c  sub     rsp, 80h
0x18001ed23  mov     rsi, rcx
0x18001ed26  lea     r12, WPP_GLOBAL_Control
0x18001ed2d  mov     rax, cs:WPP_GLOBAL_Control
0x18001ed34  mov     bl, 1
0x18001ed36  cmp     rax, r12
0x18001ed39  jz      short loc_18001ED4B
0x18001ed3b  test    [rax+1Ch], bl
0x18001ed3e  jz      short loc_18001ED4B
0x18001ed40  cmp     byte ptr [rax+19h], 4
0x18001ed44  jb      short loc_18001ED4B
0x18001ed46  mov     dil, bl
0x18001ed49  jmp     short loc_18001ED4E
0x18001ed4b  xor     dil, dil
0x18001ed4e  lea     r13, WPP_RECORDER_INITIALIZED
0x18001ed55  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18001ed5c  setnz   r14b
0x18001ed60  test    dil, dil
0x18001ed63  jnz     short loc_18001ED73
0x18001ed65  test    r14b, r14b
0x18001ed68  jnz     short loc_18001ED73
0x18001ed6a  lea     r15, WPP_19b31c027c473e795a0f5fbb7cb41a6c_Traceguids
0x18001ed71  jmp     short loc_18001EDAA
0x18001ed73  call    cs:__imp_GetCurrentThreadId
0x18001ed79  mov     dword ptr [rsp+0B8h+var_78], eax; char
0x18001ed7d  lea     r15, WPP_19b31c027c473e795a0f5fbb7cb41a6c_Traceguids
0x18001ed84  mov     [rsp+0B8h+MessageGuid], r15; MessageGuid
0x18001ed89  mov     [rsp+0B8h+var_88], 0Ah; __int16
0x18001ed90  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ed97  mov     r9, [rcx+28h]; int
0x18001ed9b  mov     r8b, r14b; int
0x18001ed9e  mov     dl, dil; int
0x18001eda1  mov     rcx, [rcx+10h]; int
0x18001eda5  call    WPP_RECORDER_AND_TRACE_SF_D
0x18001edaa  mov     eax, cs:dword_1800C1058
0x18001edb0  cmp     eax, 4
0x18001edb3  jbe     loc_18001EEAF
0x18001edb9  mov     rcx, cs:qword_1800C1070
0x18001edc0  mov     rax, cs:qword_1800C1068
0x18001edc7  mov     rdx, 470000000000h
0x18001edd1  test    rdx, rax
0x18001edd4  jz      loc_18001EEAF
0x18001edda  mov     rax, rcx
0x18001eddd  and     rax, rdx
0x18001ede0  cmp     rax, rcx
0x18001ede3  jnz     loc_18001EEAF
0x18001ede9  mov     rcx, [rsi+18h]
0x18001eded  mov     eax, [rcx+80h]
0x18001edf3  mov     [rsp+0B8h+arg_0], eax
0x18001edfa  mov     rax, [rcx+78h]
0x18001edfe  mov     ecx, [rax+0C4h]
0x18001ee04  mov     [rsp+0B8h+arg_8], ecx
0x18001ee0b  lea     rax, aStopUmrdpFrame; "Stop Umrdp frame processor"
0x18001ee12  mov     [rsp+0B8h+arg_10], rax
0x18001ee1a  lea     rax, xmmword_1800C21A0
0x18001ee21  mov     [rsp+0B8h+arg_18], rax
0x18001ee29  lea     rax, aRdpavenc; "RdpAvenc"
0x18001ee30  mov     [rsp+0B8h+var_58], rax
0x18001ee35  mov     [rsp+0B8h+var_50], 1000000h
0x18001ee3e  lea     rax, aCheckpoint; "Checkpoint"
0x18001ee45  mov     [rsp+0B8h+var_48], rax
0x18001ee4a  lea     rax, [rsp+0B8h+arg_0]
0x18001ee52  mov     [rsp+0B8h+var_68], rax
0x18001ee57  lea     rax, [rsp+0B8h+arg_8]
0x18001ee5f  mov     [rsp+0B8h+var_70], rax
0x18001ee64  lea     rax, [rsp+0B8h+arg_10]
0x18001ee6c  mov     qword ptr [rsp+0B8h+var_78], rax
0x18001ee71  lea     rax, [rsp+0B8h+arg_18]
0x18001ee79  mov     [rsp+0B8h+MessageGuid], rax
0x18001ee7e  lea     rax, [rsp+0B8h+var_58]
0x18001ee83  mov     qword ptr [rsp+0B8h+var_88], rax
0x18001ee88  lea     rax, [rsp+0B8h+var_50]
0x18001ee8d  mov     qword ptr [rsp+0B8h+var_90], rax
0x18001ee92  lea     rax, [rsp+0B8h+var_48]
0x18001ee97  mov     qword ptr [rsp+0B8h+var_98], rax
0x18001ee9c  lea     rdx, byte_1800AD033
0x18001eea3  lea     rcx, dword_1800C1058
0x18001eeaa  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@6@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001eeaf  mov     rax, [rsi+18h]
0x18001eeb3  mov     edx, [rax+80h]
0x18001eeb9  mov     [rsp+0B8h+var_90], edx; int
0x18001eebd  mov     [rsp+0B8h+var_98], 4Ah ; 'J'; int
0x18001eec5  lea     r9, aOnecoreuapTerm_56; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18001eecc  lea     r8, aRdpAvencUmrdpC_30; "Rdp::Avenc::Umrdp::CFrameProcessor<stru"...
0x18001eed3  lea     rdx, aUmrdpframeproc_0; "UmrdpFrameProcessorStop: Id %d"
0x18001eeda  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18001eee1  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18001eee6  lea     rcx, [rsi-50h]
0x18001eeea  call    ?DestroyRdpSurface@?$CFrameProcessor@UIGpuFrameProcessor@Avenc@Rdp@@@Umrdp@Avenc@Rdp@@IEAAXXZ; Rdp::Avenc::Umrdp::CFrameProcessor<Rdp::Avenc::IGpuFrameProcessor>::DestroyRdpSurface(void)
0x18001eeef  nop
0x18001eef0  mov     rcx, [rsi+18h]
0x18001eef4  mov     qword ptr [rsi+18h], 0
0x18001eefc  test    rcx, rcx
0x18001eeff  jz      short loc_18001EF0E
0x18001ef01  mov     rax, [rcx]
0x18001ef04  mov     rax, [rax+10h]
0x18001ef08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef0d  nop
0x18001ef0e  mov     rax, cs:WPP_GLOBAL_Control
0x18001ef15  cmp     rax, r12
0x18001ef18  jz      short loc_18001EF25
0x18001ef1a  test    [rax+1Ch], bl
0x18001ef1d  jz      short loc_18001EF25
0x18001ef1f  cmp     byte ptr [rax+19h], 4
0x18001ef23  jnb     short loc_18001EF27
0x18001ef25  xor     bl, bl
0x18001ef27  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18001ef2e  setnz   dil
0x18001ef32  test    bl, bl
0x18001ef34  jnz     short loc_18001EF3B
0x18001ef36  test    dil, dil
0x18001ef39  jz      short loc_18001EF6A
0x18001ef3b  call    cs:__imp_GetCurrentThreadId
0x18001ef41  mov     dword ptr [rsp+0B8h+var_78], eax; char
0x18001ef45  mov     [rsp+0B8h+MessageGuid], r15; MessageGuid
0x18001ef4a  mov     [rsp+0B8h+var_88], 0Bh; __int16
0x18001ef51  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ef58  mov     r9, [rcx+28h]; int
0x18001ef5c  mov     r8b, dil; int
0x18001ef5f  mov     dl, bl; int
0x18001ef61  mov     rcx, [rcx+10h]; int
0x18001ef65  call    WPP_RECORDER_AND_TRACE_SF_D
0x18001ef6a  xor     eax, eax
0x18001ef6c  jmp     short loc_18001EF75
0x18001ef6e  mov     eax, [rsp+0B8h+arg_0]
0x18001ef75  add     rsp, 80h
0x18001ef7c  pop     r15
0x18001ef7e  pop     r14
0x18001ef80  pop     r13
0x18001ef82  pop     r12
0x18001ef84  pop     rdi
0x18001ef85  pop     rsi
0x18001ef86  pop     rbx
0x18001ef87  retn
```
