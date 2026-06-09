# Rdp::Stack::Shim::CMonitorShim::Start(void)

- ea: `0x18001e824`
- end: `0x18001ec7e`
- name: `?Start@CMonitorShim@Shim@Stack@Rdp@@QEAAXXZ`
- size: `1114`
- prototype: `void __fastcall(Rdp::Stack::Shim::CMonitorShim *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180018afc`

## callees

- `0x18000141c`
- `0x180001574`
- `0x180007b28`
- `0x18000b0ac`
- `0x18000b130`
- `0x18000cf28`
- `0x18000d590`
- `0x18000d858`
- `0x18000db64`
- `0x18000dbf4`
- `0x18000f30c`
- `0x18000fc30`
- `0x18001cdfc`
- `0x18001e824`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e887`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ec09`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e887`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ec09`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18001e9b8`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18001e9b8`

## string_xrefs

- `0x18001e9c2`: `Failed to create property store`
- `0x18001ec6c`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18001eaf9`: `CreateMonitor failed`

## pseudocode

```c
void __fastcall Rdp::Stack::Shim::CMonitorShim::Start(Rdp::Stack::Shim::CMonitorShim *this)
{
  char v2; // di
  bool v3; // bl
  bool v4; // r14
  char CurrentThreadId; // al
  int v6; // r8d
  int v7; // edx
  int v8; // r8d
  int v9; // r9d
  unsigned int v10; // eax
  const struct _tagpropertykey *v11; // rax
  const struct _GUID *v12; // r9
  unsigned int v13; // eax
  __int64 v14; // rax
  unsigned int v15; // r9d
  unsigned int v16; // eax
  __int64 v17; // rax
  unsigned int v18; // r9d
  unsigned int v19; // eax
  __int64 *v20; // rcx
  __int64 v21; // rax
  unsigned int v22; // eax
  _QWORD *v23; // r14
  int v24; // eax
  int v25; // ebx
  unsigned int v26; // eax
  unsigned int v27; // eax
  bool v28; // bl
  char v29; // al
  int v30; // r8d
  int v31; // edx
  int v32; // [rsp+20h] [rbp-60h]
  int v33; // [rsp+20h] [rbp-60h]
  int v34; // [rsp+20h] [rbp-60h]
  char *v35; // [rsp+28h] [rbp-58h]
  char *v36; // [rsp+28h] [rbp-58h]
  char *v37; // [rsp+28h] [rbp-58h]
  char *v38; // [rsp+28h] [rbp-58h]
  char *v39; // [rsp+28h] [rbp-58h]
  char *v40; // [rsp+28h] [rbp-58h]
  char *v41; // [rsp+28h] [rbp-58h]
  int v42; // [rsp+28h] [rbp-58h]
  __int128 *v43; // [rsp+50h] [rbp-30h] BYREF
  const char *v44; // [rsp+58h] [rbp-28h] BYREF
  char v45[8]; // [rsp+60h] [rbp-20h] BYREF
  _QWORD v46[3]; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  int v48; // [rsp+C0h] [rbp+40h] BYREF
  void *ppv; // [rsp+C8h] [rbp+48h] BYREF
  __int64 (__fastcall ***v50)(_QWORD, GUID *, char *); // [rsp+D0h] [rbp+50h] BYREF
  const char *v51; // [rsp+D8h] [rbp+58h] BYREF

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
      v32,
      (int)v35,
      10,
      &WPP_9429e1887f2b37205431ce51b91c21ec_Traceguids,
      CurrentThreadId);
  }
  if ( (unsigned int)dword_18003C058 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18003C058, 0x470000000000LL) )
  {
    v48 = *(_DWORD *)(*((_QWORD *)this + 29) + 336LL);
    v51 = "Start monitor shim";
    v43 = &xmmword_18003CA50;
    v44 = "RdpLite";
    *(_QWORD *)v45 = 0x1000000;
    v46[0] = "Checkpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_18003C058,
      (unsigned int)&dword_180035EE4,
      v8,
      v9,
      (__int64)v46,
      (__int64)v45,
      (__int64)&v44,
      (__int64)&v43,
      (__int64)&v51,
      (__int64)&v48);
  }
  Rdp::Modern::Utils::CInflightRecorder::push0(
    (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
    L"MonitorShimStart",
    "Rdp::Stack::Shim::CMonitorShim::Start",
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
    0x5Cu);
  ppv = 0;
  wil::com_ptr_t<IRDPCoreChannelManager,wil::err_exception_policy>::reset(&ppv);
  v10 = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x66,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
    (const char *)v10,
    (int)"Failed to create property store",
    v35);
  v11 = (const struct _tagpropertykey *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 40LL))(*((_QWORD *)this + 30));
  v13 = Rdp::Utils::Props::IPropertyStore_SetCLSID(
          (Rdp::Utils::Props *)ppv,
          (struct IPropertyStore *)&PKEY_Monitor_Id,
          v11,
          v12);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x6D,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
    (const char *)v13,
    (int)"Failed to set PKEY_Monitor_Id property",
    v36);
  v14 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 64LL))(*((_QWORD *)this + 30));
  v16 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          (Rdp::Utils::Props *)ppv,
          (struct IPropertyStore *)&PKEY_Physical_Width,
          (const struct _tagpropertykey *)*(unsigned int *)(v14 + 8),
          v15);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x74,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
    (const char *)v16,
    (int)"Failed to set PKEY_Physical_Width property",
    v37);
  v17 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 64LL))(*((_QWORD *)this + 30));
  v19 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          (Rdp::Utils::Props *)ppv,
          (struct IPropertyStore *)&PKEY_Physical_Height,
          (const struct _tagpropertykey *)*(unsigned int *)(v17 + 12),
          v18);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x7B,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
    (const char *)v19,
    (int)"Failed to set PKEY_Physical_Height property",
    v38);
  std::unique_lock<std::mutex>::unique_lock<std::mutex>(v46, (char *)this + 144);
  v50 = 0;
  v20 = *(__int64 **)(*((_QWORD *)this + 29) + 344LL);
  v21 = *v20;
  v50 = 0;
  v22 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, void *))(v21 + 56))(v20, &v50, ppv);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x87,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
    (const char *)v22,
    (int)"CreateMonitor failed",
    v39);
  v23 = (_QWORD *)((char *)this + 224);
  wil::com_ptr_t<IRDPCoreChannelManager,wil::err_exception_policy>::reset((char *)this + 224);
  if ( v50 )
  {
    v24 = (**v50)(v50, &GUID_3abc23a0_4a59_4064_b114_d56a60c75c0a, (char *)this + 224);
    if ( v24 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v24,
        v33);
  }
  else
  {
    *v23 = 0;
  }
  v25 = Rdp::Stack::Shim::CMonitorShim::ApplyMonitorConfiguration(this);
  v26 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v23 + 32LL))(*v23);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x97,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
    (const char *)v26,
    (int)"Failed to start monitor encoding context",
    v40);
  v27 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v23 + 64LL))(*v23, v25 | 0x8000u);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x9A,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
    (const char *)v27,
    (int)"Failed to change monitor mode",
    v41);
  *((_BYTE *)this + 248) = 1;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
  {
    v2 = 0;
  }
  v28 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v29 = GetCurrentThreadId();
    LOBYTE(v30) = v28;
    LOBYTE(v31) = v2;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v31,
      v30,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v34,
      v42,
      11,
      &WPP_9429e1887f2b37205431ce51b91c21ec_Traceguids,
      v29);
  }
  wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&v50);
  std::unique_lock<Rdp::Utils::Synchronization::rundown_mutex>::~unique_lock<Rdp::Utils::Synchronization::rundown_mutex>(v46);
  wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&ppv);
}

```

## disassembly

```asm
0x18001e824  push    rbp
0x18001e826  push    rbx
0x18001e827  push    rsi
0x18001e828  push    rdi
0x18001e829  push    r12
0x18001e82b  push    r13
0x18001e82d  push    r14
0x18001e82f  mov     rbp, rsp
0x18001e832  sub     rsp, 80h
0x18001e839  mov     rsi, rcx
0x18001e83c  lea     rcx, WPP_GLOBAL_Control
0x18001e843  mov     dil, 1
0x18001e846  mov     rax, cs:WPP_GLOBAL_Control
0x18001e84d  cmp     rax, rcx
0x18001e850  jz      short loc_18001E863
0x18001e852  test    [rax+1Ch], dil
0x18001e856  jz      short loc_18001E863
0x18001e858  cmp     byte ptr [rax+19h], 4
0x18001e85c  jb      short loc_18001E863
0x18001e85e  mov     bl, dil
0x18001e861  jmp     short loc_18001E865
0x18001e863  xor     bl, bl
0x18001e865  lea     r12, WPP_RECORDER_INITIALIZED
0x18001e86c  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18001e873  setnz   r14b
0x18001e877  lea     r13, WPP_9429e1887f2b37205431ce51b91c21ec_Traceguids
0x18001e87e  test    bl, bl
0x18001e880  jnz     short loc_18001E887
0x18001e882  test    r14b, r14b
0x18001e885  jz      short loc_18001E8B6
0x18001e887  call    cs:__imp_GetCurrentThreadId
0x18001e88d  mov     dword ptr [rsp+80h+var_40], eax; char
0x18001e891  mov     [rsp+80h+MessageGuid], r13; MessageGuid
0x18001e896  mov     [rsp+80h+var_50], 0Ah; __int16
0x18001e89d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e8a4  mov     r9, [rcx+28h]; int
0x18001e8a8  mov     r8b, r14b; int
0x18001e8ab  mov     dl, bl; int
0x18001e8ad  mov     rcx, [rcx+10h]; int
0x18001e8b1  call    WPP_RECORDER_AND_TRACE_SF_D
0x18001e8b6  mov     eax, cs:dword_18003C058
0x18001e8bc  cmp     eax, 4
0x18001e8bf  jbe     loc_18001E970
0x18001e8c5  mov     rdx, 470000000000h
0x18001e8cf  lea     rcx, dword_18003C058
0x18001e8d6  call    _tlgKeywordOn
0x18001e8db  test    al, al
0x18001e8dd  jz      loc_18001E970
0x18001e8e3  mov     rax, [rsi+0E8h]
0x18001e8ea  mov     ecx, [rax+150h]
0x18001e8f0  mov     [rbp+arg_0], ecx
0x18001e8f3  lea     rax, aStartMonitorSh; "Start monitor shim"
0x18001e8fa  mov     [rbp+arg_18], rax
0x18001e8fe  lea     rax, xmmword_18003CA50
0x18001e905  mov     [rbp+var_30], rax
0x18001e909  lea     rax, aRdplite; "RdpLite"
0x18001e910  mov     [rbp+var_28], rax
0x18001e914  mov     qword ptr [rbp+var_20], 1000000h
0x18001e91c  lea     rax, aCheckpoint; "Checkpoint"
0x18001e923  mov     [rbp+var_18], rax
0x18001e927  lea     rax, [rbp+arg_0]
0x18001e92b  mov     [rsp+80h+var_38], rax
0x18001e930  lea     rax, [rbp+arg_18]
0x18001e934  mov     qword ptr [rsp+80h+var_40], rax
0x18001e939  lea     rax, [rbp+var_30]
0x18001e93d  mov     [rsp+80h+MessageGuid], rax
0x18001e942  lea     rax, [rbp+var_28]
0x18001e946  mov     qword ptr [rsp+80h+var_50], rax
0x18001e94b  lea     rax, [rbp+var_20]
0x18001e94f  mov     [rsp+80h+var_58], rax; int
0x18001e954  lea     rax, [rbp+var_18]
0x18001e958  mov     qword ptr [rsp+80h+var_60], rax
0x18001e95d  lea     rdx, dword_180035EE4
0x18001e964  lea     rcx, dword_18003C058
0x18001e96b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001e970  mov     [rsp+80h+var_60], 5Ch ; '\'; unsigned int
0x18001e978  lea     rbx, aOnecoreuapTerm_18; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18001e97f  mov     r9, rbx; char *
0x18001e982  lea     r8, aRdpStackShimCm_4; "Rdp::Stack::Shim::CMonitorShim::Start"
0x18001e989  lea     rdx, aMonitorshimsta; "MonitorShimStart"
0x18001e990  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18001e997  call    ?push0@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1I@Z; Rdp::Modern::Utils::CInflightRecorder::push0(ushort const *,char const *,char const *,uint)
0x18001e99c  mov     [rbp+ppv], 0
0x18001e9a4  lea     rcx, [rbp+ppv]
0x18001e9a8  call    ?reset@?$com_ptr_t@UIRDPCoreChannelManager@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IRDPCoreChannelManager,wil::err_exception_policy>::reset(void)
0x18001e9ad  lea     rdx, [rbp+ppv]; ppv
0x18001e9b1  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x18001e9b8  call    cs:__imp_PSCreateMemoryPropertyStore
0x18001e9be  mov     rcx, [rbp+38h]; this
0x18001e9c2  lea     rdx, aFailedToCreate_5; "Failed to create property store"
0x18001e9c9  mov     qword ptr [rsp+80h+var_60], rdx; int
0x18001e9ce  mov     r9d, eax; char *
0x18001e9d1  mov     r8, rbx; unsigned int
0x18001e9d4  mov     edx, 66h ; 'f'; void *
0x18001e9d9  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001e9de  mov     rcx, [rsi+0F0h]
0x18001e9e5  mov     rax, [rcx]
0x18001e9e8  mov     rax, [rax+28h]
0x18001e9ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e9f1  mov     r8, rax; struct _tagpropertykey *
0x18001e9f4  lea     rdx, PKEY_Monitor_Id; struct IPropertyStore *
0x18001e9fb  mov     rcx, [rbp+ppv]; this
0x18001e9ff  call    ?IPropertyStore_SetCLSID@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@AEBU_GUID@@@Z; Rdp::Utils::Props::IPropertyStore_SetCLSID(IPropertyStore *,_tagpropertykey const &,_GUID const &)
0x18001ea04  mov     rcx, [rbp+38h]; this
0x18001ea08  lea     rdx, aFailedToSetPke_10; "Failed to set PKEY_Monitor_Id property"
0x18001ea0f  mov     qword ptr [rsp+80h+var_60], rdx; int
0x18001ea14  mov     r9d, eax; char *
0x18001ea17  mov     r8, rbx; unsigned int
0x18001ea1a  mov     edx, 6Dh ; 'm'; void *
0x18001ea1f  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001ea24  mov     rcx, [rsi+0F0h]
0x18001ea2b  mov     rax, [rcx]
0x18001ea2e  mov     rax, [rax+40h]
0x18001ea32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea37  mov     r8d, [rax+8]; struct _tagpropertykey *
0x18001ea3b  lea     rdx, PKEY_Physical_Width; struct IPropertyStore *
0x18001ea42  mov     rcx, [rbp+ppv]; this
0x18001ea46  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x18001ea4b  mov     rcx, [rbp+38h]; this
0x18001ea4f  lea     rdx, aFailedToSetPke_39; "Failed to set PKEY_Physical_Width prope"...
0x18001ea56  mov     qword ptr [rsp+80h+var_60], rdx; int
0x18001ea5b  mov     r9d, eax; char *
0x18001ea5e  mov     r8, rbx; unsigned int
0x18001ea61  mov     edx, 74h ; 't'; void *
0x18001ea66  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001ea6b  mov     rcx, [rsi+0F0h]
0x18001ea72  mov     rax, [rcx]
0x18001ea75  mov     rax, [rax+40h]
0x18001ea79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea7e  mov     r8d, [rax+0Ch]; struct _tagpropertykey *
0x18001ea82  lea     rdx, PKEY_Physical_Height; struct IPropertyStore *
0x18001ea89  mov     rcx, [rbp+ppv]; this
0x18001ea8d  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x18001ea92  mov     rcx, [rbp+38h]; this
0x18001ea96  lea     rdx, aFailedToSetPke_29; "Failed to set PKEY_Physical_Height prop"...
0x18001ea9d  mov     qword ptr [rsp+80h+var_60], rdx; int
0x18001eaa2  mov     r9d, eax; char *
0x18001eaa5  mov     r8, rbx; unsigned int
0x18001eaa8  mov     edx, 7Bh ; '{'; void *
0x18001eaad  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001eab2  lea     rdx, [rsi+90h]
0x18001eab9  lea     rcx, [rbp+var_18]
0x18001eabd  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x18001eac2  nop
0x18001eac3  mov     [rbp+arg_10], 0
0x18001eacb  mov     rax, [rsi+0E8h]
0x18001ead2  mov     rcx, [rax+158h]
0x18001ead9  mov     rax, [rcx]
0x18001eadc  mov     [rbp+arg_10], 0
0x18001eae4  mov     r8, [rbp+ppv]
0x18001eae8  lea     rdx, [rbp+arg_10]
0x18001eaec  mov     rax, [rax+38h]
0x18001eaf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eaf5  mov     rcx, [rbp+38h]; this
0x18001eaf9  lea     rdx, aCreatemonitorF; "CreateMonitor failed"
0x18001eb00  mov     qword ptr [rsp+80h+var_60], rdx; int
0x18001eb05  mov     r9d, eax; char *
0x18001eb08  mov     r8, rbx; unsigned int
0x18001eb0b  mov     edx, 87h; void *
0x18001eb10  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001eb15  lea     r14, [rsi+0E0h]
0x18001eb1c  mov     rcx, r14
0x18001eb1f  call    ?reset@?$com_ptr_t@UIRDPCoreChannelManager@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IRDPCoreChannelManager,wil::err_exception_policy>::reset(void)
0x18001eb24  mov     rcx, [rbp+arg_10]
0x18001eb28  test    rcx, rcx
0x18001eb2b  jz      short loc_18001EB50
0x18001eb2d  mov     rax, [rcx]
0x18001eb30  mov     r8, r14
0x18001eb33  lea     rdx, _GUID_3abc23a0_4a59_4064_b114_d56a60c75c0a
0x18001eb3a  mov     rax, [rax]
0x18001eb3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb42  mov     rcx, [rbp+38h]; this
0x18001eb46  test    eax, eax
0x18001eb48  js      loc_18001EC69
0x18001eb4e  jmp     short loc_18001EB57
0x18001eb50  mov     qword ptr [r14], 0
0x18001eb57  mov     rcx, rsi
0x18001eb5a  call    ?ApplyMonitorConfiguration@CMonitorShim@Shim@Stack@Rdp@@QEAA?AW4AVENC_MONITOR_UPDATE_FLAGS@Avenc@4@XZ; Rdp::Stack::Shim::CMonitorShim::ApplyMonitorConfiguration(void)
0x18001eb5f  mov     ebx, eax
0x18001eb61  mov     rcx, [r14]
0x18001eb64  mov     rdx, [rcx]
0x18001eb67  mov     rax, [rdx+20h]
0x18001eb6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb70  mov     rcx, [rbp+38h]; this
0x18001eb74  lea     rdx, aFailedToStartM; "Failed to start monitor encoding contex"...
0x18001eb7b  mov     qword ptr [rsp+80h+var_60], rdx; int
0x18001eb80  mov     r9d, eax; char *
0x18001eb83  lea     r8, aOnecoreuapTerm_18; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18001eb8a  mov     edx, 97h; void *
0x18001eb8f  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001eb94  mov     rcx, [r14]
0x18001eb97  mov     rax, [rcx]
0x18001eb9a  bts     ebx, 0Fh
0x18001eb9e  mov     edx, ebx
0x18001eba0  mov     rax, [rax+40h]
0x18001eba4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eba9  mov     rcx, [rbp+38h]; this
0x18001ebad  lea     rdx, aFailedToChange; "Failed to change monitor mode"
0x18001ebb4  mov     qword ptr [rsp+80h+var_60], rdx; int
0x18001ebb9  mov     r9d, eax; char *
0x18001ebbc  lea     r8, aOnecoreuapTerm_18; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18001ebc3  mov     edx, 9Ah; void *
0x18001ebc8  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001ebcd  mov     [rsi+0F8h], dil
0x18001ebd4  mov     rax, cs:WPP_GLOBAL_Control
0x18001ebdb  lea     rcx, WPP_GLOBAL_Control
0x18001ebe2  cmp     rax, rcx
0x18001ebe5  jz      short loc_18001EBF3
0x18001ebe7  test    [rax+1Ch], dil
0x18001ebeb  jz      short loc_18001EBF3
0x18001ebed  cmp     byte ptr [rax+19h], 4
0x18001ebf1  jnb     short loc_18001EBF6
0x18001ebf3  xor     dil, dil
0x18001ebf6  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18001ebfd  setnz   bl
0x18001ec00  test    dil, dil
0x18001ec03  jnz     short loc_18001EC09
0x18001ec05  test    bl, bl
0x18001ec07  jz      short loc_18001EC3A
0x18001ec09  call    cs:__imp_GetCurrentThreadId
0x18001ec0f  mov     dword ptr [rsp+80h+var_40], eax; char
0x18001ec13  mov     [rsp+80h+MessageGuid], r13; MessageGuid
0x18001ec18  mov     [rsp+80h+var_50], 0Bh; __int16
0x18001ec1f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ec26  mov     r9, [rcx+28h]; int
0x18001ec2a  mov     r8b, bl; int
0x18001ec2d  mov     dl, dil; int
0x18001ec30  mov     rcx, [rcx+10h]; int
0x18001ec34  call    WPP_RECORDER_AND_TRACE_SF_D
0x18001ec39  nop
0x18001ec3a  lea     rcx, [rbp+arg_10]
0x18001ec3e  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x18001ec43  nop
0x18001ec44  lea     rcx, [rbp+var_18]
0x18001ec48  call    ??1?$unique_lock@Vrundown_mutex@Synchronization@Utils@Rdp@@@std@@QEAA@XZ; std::unique_lock<Rdp::Utils::Synchronization::rundown_mutex>::~unique_lock<Rdp::Utils::Synchronization::rundown_mutex>(void)
0x18001ec4d  nop
0x18001ec4e  lea     rcx, [rbp+ppv]
0x18001ec52  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x18001ec57  add     rsp, 80h
0x18001ec5e  pop     r14
0x18001ec60  pop     r13
0x18001ec62  pop     r12
0x18001ec64  pop     rdi
0x18001ec65  pop     rsi
0x18001ec66  pop     rbx
0x18001ec67  pop     rbp
0x18001ec68  retn
0x18001ec69  mov     r9d, eax; char *
0x18001ec6c  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001ec73  mov     edx, 1CBEh; void *
0x18001ec78  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
