# Rdp::Stack::Shim::CAdapterShim::Start(void)

- ea: `0x180019f08`
- end: `0x18001a299`
- name: `?Start@CAdapterShim@Shim@Stack@Rdp@@QEAAXXZ`
- size: `913`
- prototype: `void __fastcall(Rdp::Stack::Shim::CAdapterShim *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x18000cb3c`

## callees

- `0x18000141c`
- `0x180001574`
- `0x1800036f0`
- `0x180003714`
- `0x18000cf28`
- `0x18000d98c`
- `0x18000dbf4`
- `0x180018570`
- `0x180018818`
- `0x18001894c`
- `0x1800189dc`
- `0x1800193e4`
- `0x180019f08`
- `0x18001a2a0`
- `0x18001add8`
- `0x18001c230`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019f84`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a241`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019f84`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a241`

## pseudocode

```c
void __fastcall Rdp::Stack::Shim::CAdapterShim::Start(Rdp::Stack::Shim::CAdapterShim *this)
{
  char v2; // si
  bool v3; // bl
  bool v4; // di
  char CurrentThreadId; // al
  int v6; // r8d
  int v7; // edx
  int v8; // r8d
  int v9; // r9d
  char *v10; // rdx
  unsigned int v11; // eax
  char *v12; // rdi
  Rdp::Stack::Shim::CCtrlChannel **v13; // rbx
  char *v14; // rdx
  __int64 v15; // rax
  Rdp::Stack::Shim::CCtrlChannel *v16; // rcx
  __int64 v17; // rax
  Rdp::Stack::Shim::CCtrlChannel *v18; // rbx
  const unsigned __int16 *v19; // rax
  const struct _GUID *v20; // r8
  bool v21; // bl
  char v22; // al
  int v23; // r8d
  int v24; // edx
  int v25; // [rsp+20h] [rbp-59h]
  int v26; // [rsp+20h] [rbp-59h]
  int v27; // [rsp+28h] [rbp-51h]
  int v28; // [rsp+28h] [rbp-51h]
  const char *v29; // [rsp+58h] [rbp-21h] BYREF
  std::_Ref_count_base *v30; // [rsp+60h] [rbp-19h]
  int v31; // [rsp+68h] [rbp-11h] BYREF
  const char *v32; // [rsp+70h] [rbp-9h] BYREF
  __int128 *v33; // [rsp+78h] [rbp-1h] BYREF
  const char *v34; // [rsp+80h] [rbp+7h] BYREF
  __int64 v35; // [rsp+88h] [rbp+Fh] BYREF
  char v36[16]; // [rsp+90h] [rbp+17h] BYREF
  unsigned int v37[2]; // [rsp+A0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

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
      v25,
      v27,
      10,
      &WPP_c25a3f713a7c3ada5898bd1c008b2100_Traceguids,
      CurrentThreadId);
  }
  if ( (unsigned int)dword_18003C058 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18003C058, 0x470000000000LL) )
  {
    v31 = *((_DWORD *)this + 84);
    v32 = "Start adapter shim";
    v33 = &xmmword_18003CA50;
    v34 = "RdpLite";
    v35 = 0x1000000;
    v29 = "Checkpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_18003C058,
      (unsigned int)byte_180035969,
      v8,
      v9,
      (__int64)&v29,
      (__int64)&v35,
      (__int64)&v34,
      (__int64)&v33,
      (__int64)&v32,
      (__int64)&v31);
  }
  Rdp::Modern::Utils::CInflightRecorder::pushN(
    (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
    (wchar_t *)L"AdapterShimStart",
    "Rdp::Stack::Shim::CAdapterShim::Start",
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\adaptershim.cpp",
    0x61u);
  Rdp::Stack::Shim::CAdapterShim::LoadAvenc(this);
  *(_OWORD *)v36 = 0;
  *(_QWORD *)v37 = 0;
  *(_DWORD *)v36 = 24;
  v10 = v36;
  LOBYTE(v10) = 1;
  v11 = (*(__int64 (__fastcall **)(_QWORD, char *, __int64, char *, int))(**((_QWORD **)this + 19) + 64LL))(
          *((_QWORD *)this + 19),
          v10,
          24,
          v36,
          24);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x75,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\adaptershim.cpp",
    (const char *)v11,
    (int)"Failed to bind encoder and capture processes",
    v36);
  Rdp::Stack::Shim::CAdapterShim::StartProcessor(this, v37[1]);
  v12 = (char *)operator new(0x218u);
  v29 = v12;
  *(_OWORD *)v12 = 0;
  *((_DWORD *)v12 + 2) = 1;
  *((_DWORD *)v12 + 3) = 1;
  *(_QWORD *)v12 = &std::_Ref_count_obj2<Rdp::Stack::Shim::CCtrlChannel>::`vftable';
  Rdp::Stack::Shim::CCtrlChannel::CCtrlChannel((Rdp::Stack::Shim::CCtrlChannel *)(v12 + 16), this);
  v29 = v12 + 16;
  v30 = (std::_Ref_count_base *)v12;
  v13 = (Rdp::Stack::Shim::CCtrlChannel **)((char *)this + 312);
  std::shared_ptr<Rdp::Stack::Shim::CCtrlChannel>::operator=((char *)this + 312, &v29);
  if ( v30 )
    std::_Ref_count_base::_Decref(v30);
  v14 = (char *)operator new(0x20u);
  v29 = v14;
  *(_QWORD *)v14 = 0;
  *((_QWORD *)v14 + 1) = 0;
  v15 = *((_QWORD *)this + 40);
  if ( v15 )
    _InterlockedAdd((volatile signed __int32 *)(v15 + 8), 1u);
  v16 = *v13;
  *(_QWORD *)v14 = *v13;
  *((_QWORD *)v14 + 1) = *((_QWORD *)this + 40);
  *((_QWORD *)v14 + 2) = 0;
  *((_QWORD *)v14 + 3) = 0;
  v29 = 0;
  v17 = *((_QWORD *)this + 41);
  *((_QWORD *)this + 41) = v14;
  if ( v17 )
    std::default_delete<Rdp::Protocol::CRdpCtrl_Dst<Rdp::Stack::Shim::CFIoWireEncoder<Rdp::Stack::Shim::CCtrlChannel>>>::operator()(
      v16,
      v17);
  std::unique_ptr<Rdp::Protocol::CRdpCtrl_Dst<Rdp::Stack::Shim::CFIoWireEncoder<Rdp::Stack::Shim::CCtrlChannel>>>::~unique_ptr<Rdp::Protocol::CRdpCtrl_Dst<Rdp::Stack::Shim::CFIoWireEncoder<Rdp::Stack::Shim::CCtrlChannel>>>(&v29);
  v18 = *v13;
  v19 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 19) + 80LL))(*((_QWORD *)this + 19));
  Rdp::Stack::Shim::CCtrlChannel::StartFileIo(v18, v19, v20);
  *((_BYTE *)this + 96) = 1;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
  {
    v2 = 0;
  }
  v21 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v22 = GetCurrentThreadId();
    LOBYTE(v23) = v21;
    LOBYTE(v24) = v2;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v24,
      v23,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v26,
      v28,
      11,
      &WPP_c25a3f713a7c3ada5898bd1c008b2100_Traceguids,
      v22);
  }
}

```

## disassembly

```asm
0x180019f08  mov     [rsp-8+arg_8], rbx
0x180019f0d  mov     [rsp-8+arg_10], rsi
0x180019f12  push    rbp
0x180019f13  push    rdi
0x180019f14  push    r12
0x180019f16  push    r13
0x180019f18  push    r14
0x180019f1a  lea     rbp, [rsp-37h]
0x180019f1f  sub     rsp, 0B0h
0x180019f26  mov     rax, cs:__security_cookie
0x180019f2d  xor     rax, rsp
0x180019f30  mov     [rbp+57h+var_28], rax
0x180019f34  mov     r14, rcx
0x180019f37  lea     rcx, WPP_GLOBAL_Control
0x180019f3e  mov     esi, 1
0x180019f43  mov     rax, cs:WPP_GLOBAL_Control
0x180019f4a  cmp     rax, rcx
0x180019f4d  jz      short loc_180019F60
0x180019f4f  test    [rax+1Ch], sil
0x180019f53  jz      short loc_180019F60
0x180019f55  cmp     byte ptr [rax+19h], 4
0x180019f59  jb      short loc_180019F60
0x180019f5b  mov     bl, sil
0x180019f5e  jmp     short loc_180019F62
0x180019f60  xor     bl, bl
0x180019f62  lea     r12, WPP_RECORDER_INITIALIZED
0x180019f69  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180019f70  setnz   dil
0x180019f74  lea     r13, WPP_c25a3f713a7c3ada5898bd1c008b2100_Traceguids
0x180019f7b  test    bl, bl
0x180019f7d  jnz     short loc_180019F84
0x180019f7f  test    dil, dil
0x180019f82  jz      short loc_180019FB3
0x180019f84  call    cs:__imp_GetCurrentThreadId
0x180019f8a  mov     dword ptr [rsp+0D0h+var_90], eax; char
0x180019f8e  mov     [rsp+0D0h+MessageGuid], r13; MessageGuid
0x180019f93  mov     [rsp+0D0h+var_A0], 0Ah; __int16
0x180019f9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180019fa1  mov     r9, [rcx+28h]; int
0x180019fa5  mov     r8b, dil; int
0x180019fa8  mov     dl, bl; int
0x180019faa  mov     rcx, [rcx+10h]; int
0x180019fae  call    WPP_RECORDER_AND_TRACE_SF_D
0x180019fb3  mov     eax, cs:dword_18003C058
0x180019fb9  cmp     eax, 4
0x180019fbc  jbe     loc_18001A067
0x180019fc2  mov     rdx, 470000000000h
0x180019fcc  lea     rcx, dword_18003C058
0x180019fd3  call    _tlgKeywordOn
0x180019fd8  test    al, al
0x180019fda  jz      loc_18001A067
0x180019fe0  mov     eax, [r14+150h]
0x180019fe7  mov     [rbp+57h+var_68], eax
0x180019fea  lea     rax, aStartAdapterSh; "Start adapter shim"
0x180019ff1  mov     [rbp+57h+var_60], rax
0x180019ff5  lea     rax, xmmword_18003CA50
0x180019ffc  mov     [rbp+57h+var_58], rax
0x18001a000  lea     rax, aRdplite; "RdpLite"
0x18001a007  mov     [rbp+57h+var_50], rax
0x18001a00b  mov     [rbp+57h+var_48], 1000000h
0x18001a013  lea     rax, aCheckpoint; "Checkpoint"
0x18001a01a  mov     [rbp+57h+var_78], rax
0x18001a01e  lea     rax, [rbp+57h+var_68]
0x18001a022  mov     [rsp+0D0h+var_88], rax
0x18001a027  lea     rax, [rbp+57h+var_60]
0x18001a02b  mov     qword ptr [rsp+0D0h+var_90], rax
0x18001a030  lea     rax, [rbp+57h+var_58]
0x18001a034  mov     [rsp+0D0h+MessageGuid], rax
0x18001a039  lea     rax, [rbp+57h+var_50]
0x18001a03d  mov     qword ptr [rsp+0D0h+var_A0], rax
0x18001a042  lea     rax, [rbp+57h+var_48]
0x18001a046  mov     [rsp+0D0h+var_A8], rax
0x18001a04b  lea     rax, [rbp+57h+var_78]
0x18001a04f  mov     qword ptr [rsp+0D0h+var_B0], rax
0x18001a054  lea     rdx, byte_180035969
0x18001a05b  lea     rcx, dword_18003C058
0x18001a062  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001a067  mov     [rsp+0D0h+var_B0], 61h ; 'a'; unsigned int
0x18001a06f  lea     r9, aOnecoreuapTerm_25; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18001a076  lea     r8, aRdpStackShimCa_7; "Rdp::Stack::Shim::CAdapterShim::Start"
0x18001a07d  lea     rdx, aAdaptershimsta; "AdapterShimStart"
0x18001a084  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18001a08b  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18001a090  mov     rcx, r14; this
0x18001a093  call    ?LoadAvenc@CAdapterShim@Shim@Stack@Rdp@@AEAAXXZ; Rdp::Stack::Shim::CAdapterShim::LoadAvenc(void)
0x18001a098  xorps   xmm0, xmm0
0x18001a09b  xor     eax, eax
0x18001a09d  movups  xmmword ptr [rbp+57h+var_40], xmm0
0x18001a0a1  mov     qword ptr [rbp+57h+var_30], rax
0x18001a0a5  lea     r8d, [rax+18h]
0x18001a0a9  mov     dword ptr [rbp+57h+var_40], r8d
0x18001a0ad  mov     [rbp+57h+var_80], eax
0x18001a0b0  mov     rcx, [r14+98h]
0x18001a0b7  mov     rax, [rcx]
0x18001a0ba  lea     rdx, [rbp+57h+var_80]
0x18001a0be  mov     qword ptr [rsp+0D0h+var_A0], rdx
0x18001a0c3  lea     rdx, [rbp+57h+var_40]
0x18001a0c7  mov     [rsp+0D0h+var_A8], rdx; int
0x18001a0cc  mov     [rsp+0D0h+var_B0], r8d
0x18001a0d1  lea     r9, [rbp+57h+var_40]
0x18001a0d5  mov     dl, sil
0x18001a0d8  mov     rax, [rax+40h]
0x18001a0dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0e1  mov     rcx, [rbp+5Fh]; this
0x18001a0e5  lea     rdx, aFailedToBindEn; "Failed to bind encoder and capture proc"...
0x18001a0ec  mov     qword ptr [rsp+0D0h+var_B0], rdx; int
0x18001a0f1  mov     r9d, eax; char *
0x18001a0f4  lea     r8, aOnecoreuapTerm_25; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18001a0fb  mov     edx, 75h ; 'u'; void *
0x18001a100  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001a105  mov     edx, [rbp+57h+var_30+4]; unsigned int
0x18001a108  mov     rcx, r14; this
0x18001a10b  call    ?StartProcessor@CAdapterShim@Shim@Stack@Rdp@@AEAAXI@Z; Rdp::Stack::Shim::CAdapterShim::StartProcessor(uint)
0x18001a110  mov     ecx, 218h; Size
0x18001a115  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a11a  mov     rdi, rax
0x18001a11d  mov     [rbp+57h+var_78], rax
0x18001a121  xorps   xmm0, xmm0
0x18001a124  movups  xmmword ptr [rax], xmm0
0x18001a127  mov     [rax+8], esi
0x18001a12a  mov     [rax+0Ch], esi
0x18001a12d  lea     rax, ??_7?$_Ref_count_obj2@VCCtrlChannel@Shim@Stack@Rdp@@@std@@6B@; const std::_Ref_count_obj2<Rdp::Stack::Shim::CCtrlChannel>::`vftable'
0x18001a134  mov     [rdi], rax
0x18001a137  lea     rbx, [rdi+10h]
0x18001a13b  mov     rdx, r14; struct Rdp::Stack::Shim::CAdapterShim *
0x18001a13e  mov     rcx, rbx; this
0x18001a141  call    ??0CCtrlChannel@Shim@Stack@Rdp@@QEAA@PEAVCAdapterShim@123@@Z; Rdp::Stack::Shim::CCtrlChannel::CCtrlChannel(Rdp::Stack::Shim::CAdapterShim *)
0x18001a146  nop
0x18001a147  mov     [rbp+57h+var_78], rbx
0x18001a14b  mov     [rbp+57h+var_70], rdi
0x18001a14f  lea     rbx, [r14+138h]
0x18001a156  lea     rdx, [rbp+57h+var_78]
0x18001a15a  mov     rcx, rbx
0x18001a15d  call    ??4?$shared_ptr@VCCtrlChannel@Shim@Stack@Rdp@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Rdp::Stack::Shim::CCtrlChannel>::operator=(std::shared_ptr<Rdp::Stack::Shim::CCtrlChannel> &&)
0x18001a162  mov     rcx, [rbp+57h+var_70]; this
0x18001a166  test    rcx, rcx
0x18001a169  jz      short loc_18001A170
0x18001a16b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001a170  mov     ecx, 20h ; ' '; Size
0x18001a175  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a17a  mov     rdx, rax
0x18001a17d  mov     [rbp+57h+var_78], rax
0x18001a181  mov     qword ptr [rax], 0
0x18001a188  mov     qword ptr [rax+8], 0
0x18001a190  mov     rax, [rbx+8]
0x18001a194  test    rax, rax
0x18001a197  jz      short loc_18001A19D
0x18001a199  lock add [rax+8], esi
0x18001a19d  mov     rcx, [rbx]
0x18001a1a0  mov     [rdx], rcx
0x18001a1a3  mov     rax, [rbx+8]
0x18001a1a7  mov     [rdx+8], rax
0x18001a1ab  mov     qword ptr [rdx+10h], 0
0x18001a1b3  mov     qword ptr [rdx+18h], 0
0x18001a1bb  mov     [rbp+57h+var_78], 0
0x18001a1c3  mov     rax, [r14+148h]
0x18001a1ca  mov     [r14+148h], rdx
0x18001a1d1  test    rax, rax
0x18001a1d4  jz      short loc_18001A1DE
0x18001a1d6  mov     rdx, rax
0x18001a1d9  call    ??R?$default_delete@V?$CRdpCtrl_Dst@V?$CFIoWireEncoder@VCCtrlChannel@Shim@Stack@Rdp@@@Shim@Stack@Rdp@@@Protocol@Rdp@@@std@@QEBAXPEAV?$CRdpCtrl_Dst@V?$CFIoWireEncoder@VCCtrlChannel@Shim@Stack@Rdp@@@Shim@Stack@Rdp@@@Protocol@Rdp@@@Z; std::default_delete<Rdp::Protocol::CRdpCtrl_Dst<Rdp::Stack::Shim::CFIoWireEncoder<Rdp::Stack::Shim::CCtrlChannel>>>::operator()(Rdp::Protocol::CRdpCtrl_Dst<Rdp::Stack::Shim::CFIoWireEncoder<Rdp::Stack::Shim::CCtrlChannel>> *)
0x18001a1de  lea     rcx, [rbp+57h+var_78]
0x18001a1e2  call    ??1?$unique_ptr@V?$CRdpCtrl_Dst@V?$CFIoWireEncoder@VCCtrlChannel@Shim@Stack@Rdp@@@Shim@Stack@Rdp@@@Protocol@Rdp@@U?$default_delete@V?$CRdpCtrl_Dst@V?$CFIoWireEncoder@VCCtrlChannel@Shim@Stack@Rdp@@@Shim@Stack@Rdp@@@Protocol@Rdp@@@std@@@std@@QEAA@XZ; std::unique_ptr<Rdp::Protocol::CRdpCtrl_Dst<Rdp::Stack::Shim::CFIoWireEncoder<Rdp::Stack::Shim::CCtrlChannel>>>::~unique_ptr<Rdp::Protocol::CRdpCtrl_Dst<Rdp::Stack::Shim::CFIoWireEncoder<Rdp::Stack::Shim::CCtrlChannel>>>(void)
0x18001a1e7  mov     rbx, [rbx]
0x18001a1ea  mov     rcx, [r14+98h]
0x18001a1f1  mov     rax, [rcx]
0x18001a1f4  mov     rax, [rax+50h]
0x18001a1f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a1fd  mov     rdx, rax; unsigned __int16 *
0x18001a200  mov     rcx, rbx; this
0x18001a203  call    ?StartFileIo@CCtrlChannel@Shim@Stack@Rdp@@AEAAXPEBGAEBU_GUID@@II@Z; Rdp::Stack::Shim::CCtrlChannel::StartFileIo(ushort const *,_GUID const &,uint,uint)
0x18001a208  mov     [r14+60h], sil
0x18001a20c  mov     rax, cs:WPP_GLOBAL_Control
0x18001a213  lea     rcx, WPP_GLOBAL_Control
0x18001a21a  cmp     rax, rcx
0x18001a21d  jz      short loc_18001A22B
0x18001a21f  test    [rax+1Ch], sil
0x18001a223  jz      short loc_18001A22B
0x18001a225  cmp     byte ptr [rax+19h], 4
0x18001a229  jnb     short loc_18001A22E
0x18001a22b  xor     sil, sil
0x18001a22e  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18001a235  setnz   bl
0x18001a238  test    sil, sil
0x18001a23b  jnz     short loc_18001A241
0x18001a23d  test    bl, bl
0x18001a23f  jz      short loc_18001A271
0x18001a241  call    cs:__imp_GetCurrentThreadId
0x18001a247  mov     dword ptr [rsp+0D0h+var_90], eax; char
0x18001a24b  mov     [rsp+0D0h+MessageGuid], r13; MessageGuid
0x18001a250  mov     [rsp+0D0h+var_A0], 0Bh; __int16
0x18001a257  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a25e  mov     r9, [rcx+28h]; int
0x18001a262  mov     r8b, bl; int
0x18001a265  mov     dl, sil; int
0x18001a268  mov     rcx, [rcx+10h]; int
0x18001a26c  call    WPP_RECORDER_AND_TRACE_SF_D
0x18001a271  mov     rcx, [rbp+57h+var_28]
0x18001a275  xor     rcx, rsp; StackCookie
0x18001a278  call    __security_check_cookie
0x18001a27d  lea     r11, [rsp+0D0h+var_20]
0x18001a285  mov     rbx, [r11+38h]
0x18001a289  mov     rsi, [r11+40h]
0x18001a28d  mov     rsp, r11
0x18001a290  pop     r14
0x18001a292  pop     r13
0x18001a294  pop     r12
0x18001a296  pop     rdi
0x18001a297  pop     rbp
0x18001a298  retn
```
