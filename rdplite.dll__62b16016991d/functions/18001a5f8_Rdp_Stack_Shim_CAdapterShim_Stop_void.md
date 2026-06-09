# Rdp::Stack::Shim::CAdapterShim::Stop(void)

- ea: `0x18001a5f8`
- end: `0x18001a8a0`
- name: `?Stop@CAdapterShim@Shim@Stack@Rdp@@QEAAXXZ`
- size: `680`
- prototype: `void __fastcall(Rdp::Stack::Shim::CAdapterShim *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000cbc0`

## callees

- `0x18000141c`
- `0x180001574`
- `0x18000cea4`
- `0x18000d858`
- `0x18000dbf4`
- `0x18001894c`
- `0x1800189dc`
- `0x180018d1c`
- `0x18001a5f8`
- `0x18001a8a8`
- `0x18001add8`
- `0x18001b34c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a651`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a85a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a651`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a85a`

## pseudocode

```c
void __fastcall Rdp::Stack::Shim::CAdapterShim::Stop(Rdp::Stack::Shim::CAdapterShim *this)
{
  char v2; // si
  bool v3; // bl
  bool v4; // r14
  char CurrentThreadId; // al
  int v6; // r8d
  int v7; // edx
  int v8; // r8d
  int v9; // r9d
  std::_Ref_count_base *v10; // rcx
  __int64 v11; // rdx
  _QWORD *v12; // rcx
  bool v13; // bl
  char v14; // al
  int v15; // r8d
  int v16; // edx
  int v17; // [rsp+20h] [rbp-50h]
  int v18; // [rsp+20h] [rbp-50h]
  int v19; // [rsp+28h] [rbp-48h]
  int v20; // [rsp+28h] [rbp-48h]
  char *v21; // [rsp+30h] [rbp-40h]
  int v22[2]; // [rsp+50h] [rbp-20h] BYREF
  std::_Ref_count_base *v23[2]; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  int v25; // [rsp+B0h] [rbp+40h] BYREF
  const char *v26; // [rsp+B8h] [rbp+48h] BYREF
  __int128 *v27; // [rsp+C0h] [rbp+50h] BYREF
  const char *v28; // [rsp+C8h] [rbp+58h] BYREF

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
      v17,
      v19,
      12,
      &WPP_c25a3f713a7c3ada5898bd1c008b2100_Traceguids,
      CurrentThreadId);
  }
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x9F,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\adaptershim.cpp",
    (const char *)0x8000FFFFLL,
    *((_BYTE *)this + 96) == 0,
    (bool)"Adapter shim is not started",
    v21);
  if ( (unsigned int)dword_18003C058 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18003C058, 0x470000000000LL) )
  {
    v25 = *((_DWORD *)this + 84);
    *(_QWORD *)v22 = 0x1000000;
    v26 = "Stop adapter shim";
    v27 = &xmmword_18003CA50;
    v28 = "RdpLite";
    v23[0] = (std::_Ref_count_base *)"Checkpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_18003C058,
      (unsigned int)word_18003590A,
      v8,
      v9,
      (__int64)v23,
      (__int64)v22,
      (__int64)&v28,
      (__int64)&v27,
      (__int64)&v26,
      (__int64)&v25);
  }
  Rdp::Modern::Utils::CInflightRecorder::push0(
    (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
    L"AdapterShimStop",
    "Rdp::Stack::Shim::CAdapterShim::Stop",
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\adaptershim.cpp",
    0xA9u);
  Rdp::Stack::Shim::CAdapterShim::StopProcessor(this);
  Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CThreadPoolIo<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&void Rdp::Utils::TP::details::DestroyThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>>>>::Close(*((_QWORD *)this + 39));
  *(_OWORD *)v23 = 0;
  std::shared_ptr<Rdp::Stack::Shim::CCtrlChannel>::operator=((char *)this + 312, v23);
  v10 = v23[1];
  if ( v23[1] )
    std::_Ref_count_base::_Decref(v23[1]);
  v11 = *((_QWORD *)this + 41);
  *((_QWORD *)this + 41) = 0;
  if ( v11 )
    std::default_delete<Rdp::Protocol::CRdpCtrl_Dst<Rdp::Stack::Shim::CFIoWireEncoder<Rdp::Stack::Shim::CCtrlChannel>>>::operator()(
      v10,
      v11);
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
    (char *)this + 136,
    0);
  v12 = (_QWORD *)((char *)this + 104);
  *(_OWORD *)((char *)this + 184) = 0;
  *(_OWORD *)((char *)this + 200) = 0;
  *((_QWORD *)this + 15) = 0;
  if ( *((_QWORD *)this + 16) > 7u )
    v12 = (_QWORD *)*v12;
  *(_WORD *)v12 = 0;
  *((_BYTE *)this + 96) = 0;
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
      v18,
      v20,
      13,
      &WPP_c25a3f713a7c3ada5898bd1c008b2100_Traceguids,
      v14);
  }
}

```

## disassembly

```asm
0x18001a5f8  push    rbp
0x18001a5fa  push    rbx
0x18001a5fb  push    rsi
0x18001a5fc  push    rdi
0x18001a5fd  push    r12
0x18001a5ff  push    r13
0x18001a601  push    r14
0x18001a603  mov     rbp, rsp
0x18001a606  sub     rsp, 70h
0x18001a60a  mov     rdi, rcx
0x18001a60d  mov     rax, cs:WPP_GLOBAL_Control
0x18001a614  lea     r13, WPP_GLOBAL_Control
0x18001a61b  mov     sil, 1
0x18001a61e  cmp     rax, r13
0x18001a621  jz      short loc_18001A634
0x18001a623  test    [rax+1Ch], sil
0x18001a627  jz      short loc_18001A634
0x18001a629  cmp     byte ptr [rax+19h], 4
0x18001a62d  jb      short loc_18001A634
0x18001a62f  mov     bl, sil
0x18001a632  jmp     short loc_18001A636
0x18001a634  xor     bl, bl
0x18001a636  lea     r12, WPP_RECORDER_INITIALIZED
0x18001a63d  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18001a644  setnz   r14b
0x18001a648  test    bl, bl
0x18001a64a  jnz     short loc_18001A651
0x18001a64c  test    r14b, r14b
0x18001a64f  jz      short loc_18001A687
0x18001a651  call    cs:__imp_GetCurrentThreadId
0x18001a657  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a65e  mov     r8b, r14b; int
0x18001a661  mov     dword ptr [rsp+70h+var_30], eax; char
0x18001a665  mov     dl, bl; int
0x18001a667  lea     rax, WPP_c25a3f713a7c3ada5898bd1c008b2100_Traceguids
0x18001a66e  mov     [rsp+70h+MessageGuid], rax; MessageGuid
0x18001a673  mov     r9, [rcx+28h]; int
0x18001a677  mov     rcx, [rcx+10h]; int
0x18001a67b  mov     word ptr [rsp+70h+var_40], 0Ch; char *
0x18001a682  call    WPP_RECORDER_AND_TRACE_SF_D
0x18001a687  cmp     byte ptr [rdi+60h], 0
0x18001a68b  lea     rdx, aAdapterShimIsN; "Adapter shim is not started"
0x18001a692  mov     rcx, [rbp+38h]; this
0x18001a696  lea     r8, aOnecoreuapTerm_25; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18001a69d  mov     qword ptr [rsp+70h+var_48], rdx; bool
0x18001a6a2  setz    al
0x18001a6a5  mov     r9d, 8000FFFFh; char *
0x18001a6ab  mov     [rsp+70h+var_50], al; char
0x18001a6af  mov     edx, 9Fh; void *
0x18001a6b4  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001a6b9  mov     eax, cs:dword_18003C058
0x18001a6bf  cmp     eax, 4
0x18001a6c2  jbe     loc_18001A76C
0x18001a6c8  mov     rdx, 470000000000h
0x18001a6d2  lea     rcx, dword_18003C058
0x18001a6d9  call    _tlgKeywordOn
0x18001a6de  test    al, al
0x18001a6e0  jz      loc_18001A76C
0x18001a6e6  mov     eax, [rdi+150h]
0x18001a6ec  lea     rdx, word_18003590A
0x18001a6f3  mov     [rbp+arg_0], eax
0x18001a6f6  lea     rcx, dword_18003C058
0x18001a6fd  lea     rax, aStopAdapterShi; "Stop adapter shim"
0x18001a704  mov     qword ptr [rbp+var_20], 1000000h
0x18001a70c  mov     [rbp+arg_8], rax
0x18001a710  lea     rax, xmmword_18003CA50
0x18001a717  mov     [rbp+arg_10], rax
0x18001a71b  lea     rax, aRdplite; "RdpLite"
0x18001a722  mov     [rbp+arg_18], rax
0x18001a726  lea     rax, aCheckpoint; "Checkpoint"
0x18001a72d  mov     [rbp+var_18], rax
0x18001a731  lea     rax, [rbp+arg_0]
0x18001a735  mov     [rsp+70h+var_28], rax
0x18001a73a  lea     rax, [rbp+arg_8]
0x18001a73e  mov     qword ptr [rsp+70h+var_30], rax
0x18001a743  lea     rax, [rbp+arg_10]
0x18001a747  mov     [rsp+70h+MessageGuid], rax
0x18001a74c  lea     rax, [rbp+arg_18]
0x18001a750  mov     [rsp+70h+var_40], rax
0x18001a755  lea     rax, [rbp+var_20]
0x18001a759  mov     qword ptr [rsp+70h+var_48], rax; int
0x18001a75e  lea     rax, [rbp+var_18]
0x18001a762  mov     qword ptr [rsp+70h+var_50], rax
0x18001a767  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001a76c  lea     r9, aOnecoreuapTerm_25; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18001a773  mov     dword ptr [rsp+70h+var_50], 0A9h; int
0x18001a77b  lea     r8, aRdpStackShimCa_0; "Rdp::Stack::Shim::CAdapterShim::Stop"
0x18001a782  lea     rdx, aAdaptershimsto; "AdapterShimStop"
0x18001a789  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18001a790  call    ?push0@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1I@Z; Rdp::Modern::Utils::CInflightRecorder::push0(ushort const *,char const *,char const *,uint)
0x18001a795  mov     rcx, rdi; this
0x18001a798  call    ?StopProcessor@CAdapterShim@Shim@Stack@Rdp@@AEAAXXZ; Rdp::Stack::Shim::CAdapterShim::StopProcessor(void)
0x18001a79d  lea     rbx, [rdi+138h]
0x18001a7a4  mov     rcx, [rbx]
0x18001a7a7  call    ?Close@?$CFileChannel@V?$CThreadPoolIo@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_IO@@P6AXPEAU1@@Z$1?DestroyThreadpoolIo@details@TP@Utils@Rdp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@TP@Utils@Rdp@@@Driver@Stack@Rdp@@QEAAXXZ; Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CThreadPoolIo<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&Rdp::Utils::TP::details::DestroyThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>>>>::Close(void)
0x18001a7ac  xorps   xmm0, xmm0
0x18001a7af  lea     rdx, [rbp+var_18]
0x18001a7b3  mov     rcx, rbx
0x18001a7b6  movdqu  xmmword ptr [rbp+var_18], xmm0
0x18001a7bb  call    ??4?$shared_ptr@VCCtrlChannel@Shim@Stack@Rdp@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Rdp::Stack::Shim::CCtrlChannel>::operator=(std::shared_ptr<Rdp::Stack::Shim::CCtrlChannel> &&)
0x18001a7c0  mov     rcx, [rbp+var_18+8]; this
0x18001a7c4  test    rcx, rcx
0x18001a7c7  jz      short loc_18001A7CE
0x18001a7c9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001a7ce  mov     rdx, [rdi+148h]
0x18001a7d5  mov     qword ptr [rdi+148h], 0
0x18001a7e0  test    rdx, rdx
0x18001a7e3  jz      short loc_18001A7EA
0x18001a7e5  call    ??R?$default_delete@V?$CRdpCtrl_Dst@V?$CFIoWireEncoder@VCCtrlChannel@Shim@Stack@Rdp@@@Shim@Stack@Rdp@@@Protocol@Rdp@@@std@@QEBAXPEAV?$CRdpCtrl_Dst@V?$CFIoWireEncoder@VCCtrlChannel@Shim@Stack@Rdp@@@Shim@Stack@Rdp@@@Protocol@Rdp@@@Z; std::default_delete<Rdp::Protocol::CRdpCtrl_Dst<Rdp::Stack::Shim::CFIoWireEncoder<Rdp::Stack::Shim::CCtrlChannel>>>::operator()(Rdp::Protocol::CRdpCtrl_Dst<Rdp::Stack::Shim::CFIoWireEncoder<Rdp::Stack::Shim::CCtrlChannel>> *)
0x18001a7ea  lea     rcx, [rdi+88h]
0x18001a7f1  xor     edx, edx
0x18001a7f3  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x18001a7f8  lea     rcx, [rdi+68h]
0x18001a7fc  xorps   xmm0, xmm0
0x18001a7ff  movdqu  xmmword ptr [rdi+0B8h], xmm0
0x18001a807  xorps   xmm1, xmm1
0x18001a80a  movdqu  xmmword ptr [rdi+0C8h], xmm1
0x18001a812  mov     qword ptr [rcx+10h], 0
0x18001a81a  cmp     qword ptr [rcx+18h], 7
0x18001a81f  jbe     short loc_18001A824
0x18001a821  mov     rcx, [rcx]
0x18001a824  xor     eax, eax
0x18001a826  mov     [rcx], ax
0x18001a829  mov     [rdi+60h], al
0x18001a82c  mov     rax, cs:WPP_GLOBAL_Control
0x18001a833  cmp     rax, r13
0x18001a836  jz      short loc_18001A844
0x18001a838  test    [rax+1Ch], sil
0x18001a83c  jz      short loc_18001A844
0x18001a83e  cmp     byte ptr [rax+19h], 4
0x18001a842  jnb     short loc_18001A847
0x18001a844  xor     sil, sil
0x18001a847  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18001a84e  setnz   bl
0x18001a851  test    sil, sil
0x18001a854  jnz     short loc_18001A85A
0x18001a856  test    bl, bl
0x18001a858  jz      short loc_18001A891
0x18001a85a  call    cs:__imp_GetCurrentThreadId
0x18001a860  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a867  mov     r8b, bl; int
0x18001a86a  mov     dword ptr [rsp+70h+var_30], eax; char
0x18001a86e  mov     dl, sil; int
0x18001a871  lea     rax, WPP_c25a3f713a7c3ada5898bd1c008b2100_Traceguids
0x18001a878  mov     [rsp+70h+MessageGuid], rax; MessageGuid
0x18001a87d  mov     r9, [rcx+28h]; int
0x18001a881  mov     rcx, [rcx+10h]; int
0x18001a885  mov     word ptr [rsp+70h+var_40], 0Dh; __int16
0x18001a88c  call    WPP_RECORDER_AND_TRACE_SF_D
0x18001a891  add     rsp, 70h
0x18001a895  pop     r14
0x18001a897  pop     r13
0x18001a899  pop     r12
0x18001a89b  pop     rdi
0x18001a89c  pop     rsi
0x18001a89d  pop     rbx
0x18001a89e  pop     rbp
0x18001a89f  retn
```
