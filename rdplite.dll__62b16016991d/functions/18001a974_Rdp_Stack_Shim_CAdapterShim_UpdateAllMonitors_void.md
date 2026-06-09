# Rdp::Stack::Shim::CAdapterShim::UpdateAllMonitors(void)

- ea: `0x18001a974`
- end: `0x18001aac1`
- name: `?UpdateAllMonitors@CAdapterShim@Shim@Stack@Rdp@@AEAAXXZ`
- size: `333`
- prototype: `void __fastcall(Rdp::Stack::Shim::CAdapterShim *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180019894`

## callees

- `0x18000141c`
- `0x1800023fc`
- `0x18000d98c`
- `0x180018360`
- `0x1800187a0`
- `0x180018990`
- `0x18001a92c`
- `0x18001a974`
- `0x18001cdfc`

## string_xrefs

- `0x18001aa56`: `AdapterShimUpdateMonitors: %d`
- `0x18001aa4f`: `Rdp::Stack::Shim::CAdapterShim::UpdateAllMonitors`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Rdp::Stack::Shim::CAdapterShim::UpdateAllMonitors(Rdp::Stack::Shim::CAdapterShim *this)
{
  int v2; // r8d
  int v3; // r9d
  __int64 v4; // rbx
  unsigned int v5; // eax
  __int64 v6; // [rsp+50h] [rbp-28h] BYREF
  _QWORD v7[4]; // [rsp+58h] [rbp-20h] BYREF
  __int64 v8; // [rsp+90h] [rbp+18h] BYREF
  __int64 v9; // [rsp+98h] [rbp+20h] BYREF
  __int128 *v10; // [rsp+A0h] [rbp+28h] BYREF
  const char *v11; // [rsp+A8h] [rbp+30h] BYREF

  if ( (unsigned int)dword_18003C058 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18003C058, 0x470000000000LL) )
  {
    v9 = *((_QWORD *)this + 21);
    LODWORD(v8) = *((_DWORD *)this + 84);
    v10 = &xmmword_18003CA50;
    v11 = "RdpLite";
    v6 = 0x1000000;
    v7[0] = "Checkpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      (unsigned int)&dword_18003C058,
      (unsigned int)word_18003558A,
      v2,
      v3,
      (__int64)v7,
      (__int64)&v6,
      (__int64)&v11,
      (__int64)&v10,
      (__int64)&v8,
      (__int64)&v9);
  }
  Rdp::Modern::Utils::CInflightRecorder::pushN(
    (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
    (wchar_t *)L"AdapterShimUpdateMonitors: %d",
    "Rdp::Stack::Shim::CAdapterShim::UpdateAllMonitors",
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\adaptershim.cpp",
    0x2B7u,
    *((_QWORD *)this + 21));
  std::shared_lock<std::shared_mutex>::shared_lock<std::shared_mutex>(v7, (char *)this + 176);
  v4 = **((_QWORD **)this + 20);
  v8 = v4;
  while ( !*(_BYTE *)(v4 + 25) )
  {
    v5 = Rdp::Stack::Shim::CMonitorShim::ApplyMonitorConfiguration(*(_QWORD *)(v4 + 48));
    Rdp::Stack::Shim::CMonitorShim::TriggerModeChange(*(_QWORD *)(v4 + 48), v5);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>>,std::_Iterator_base0>::operator++(&v8);
    v4 = v8;
  }
  std::shared_lock<std::shared_mutex>::~shared_lock<std::shared_mutex>(v7);
}

```

## disassembly

```asm
0x18001a974  push    rbp
0x18001a976  push    rbx
0x18001a977  mov     rbp, rsp
0x18001a97a  sub     rsp, 78h
0x18001a97e  mov     rbx, rcx
0x18001a981  mov     eax, cs:dword_18003C058
0x18001a987  cmp     eax, 4
0x18001a98a  jbe     loc_18001AA34
0x18001a990  mov     rdx, 470000000000h
0x18001a99a  lea     rcx, dword_18003C058
0x18001a9a1  call    _tlgKeywordOn
0x18001a9a6  test    al, al
0x18001a9a8  jz      loc_18001AA34
0x18001a9ae  mov     rax, [rbx+0A8h]
0x18001a9b5  mov     [rbp+arg_8], rax
0x18001a9b9  mov     eax, [rbx+150h]
0x18001a9bf  mov     dword ptr [rbp+arg_0], eax
0x18001a9c2  lea     rax, xmmword_18003CA50
0x18001a9c9  mov     [rbp+arg_10], rax
0x18001a9cd  lea     rax, aRdplite; "RdpLite"
0x18001a9d4  mov     [rbp+arg_18], rax
0x18001a9d8  mov     [rbp+var_28], 1000000h
0x18001a9e0  lea     rax, aCheckpoint; "Checkpoint"
0x18001a9e7  mov     [rbp+var_20], rax
0x18001a9eb  lea     rax, [rbp+arg_8]
0x18001a9ef  mov     [rsp+78h+var_30], rax
0x18001a9f4  lea     rax, [rbp+arg_0]
0x18001a9f8  mov     [rsp+78h+var_38], rax
0x18001a9fd  lea     rax, [rbp+arg_10]
0x18001aa01  mov     [rsp+78h+var_40], rax
0x18001aa06  lea     rax, [rbp+arg_18]
0x18001aa0a  mov     [rsp+78h+var_48], rax
0x18001aa0f  lea     rax, [rbp+var_28]
0x18001aa13  mov     [rsp+78h+var_50], rax
0x18001aa18  lea     rax, [rbp+var_20]
0x18001aa1c  mov     qword ptr [rsp+78h+var_58], rax
0x18001aa21  lea     rdx, word_18003558A
0x18001aa28  lea     rcx, dword_18003C058
0x18001aa2f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18001aa34  mov     rax, [rbx+0A8h]
0x18001aa3b  mov     [rsp+78h+var_50], rax
0x18001aa40  mov     [rsp+78h+var_58], 2B7h; unsigned int
0x18001aa48  lea     r9, aOnecoreuapTerm_25; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18001aa4f  lea     r8, aRdpStackShimCa_6; "Rdp::Stack::Shim::CAdapterShim::UpdateA"...
0x18001aa56  lea     rdx, aAdaptershimupd; "AdapterShimUpdateMonitors: %d"
0x18001aa5d  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18001aa64  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18001aa69  lea     rdx, [rbx+0B0h]
0x18001aa70  lea     rcx, [rbp+var_20]
0x18001aa74  call    ??0?$shared_lock@Vshared_mutex@std@@@std@@QEAA@AEAVshared_mutex@1@@Z; std::shared_lock<std::shared_mutex>::shared_lock<std::shared_mutex>(std::shared_mutex &)
0x18001aa79  nop
0x18001aa7a  mov     rbx, [rbx+0A0h]
0x18001aa81  mov     rbx, [rbx]
0x18001aa84  mov     [rbp+arg_0], rbx
0x18001aa88  cmp     byte ptr [rbx+19h], 0
0x18001aa8c  jnz     short loc_18001AAB1
0x18001aa8e  mov     rcx, [rbx+30h]
0x18001aa92  call    ?ApplyMonitorConfiguration@CMonitorShim@Shim@Stack@Rdp@@QEAA?AW4AVENC_MONITOR_UPDATE_FLAGS@Avenc@4@XZ; Rdp::Stack::Shim::CMonitorShim::ApplyMonitorConfiguration(void)
0x18001aa97  mov     edx, eax
0x18001aa99  mov     rcx, [rbx+30h]
0x18001aa9d  call    ?TriggerModeChange@CMonitorShim@Shim@Stack@Rdp@@QEAAXW4AVENC_MONITOR_UPDATE_FLAGS@Avenc@4@@Z; Rdp::Stack::Shim::CMonitorShim::TriggerModeChange(Rdp::Avenc::AVENC_MONITOR_UPDATE_FLAGS)
0x18001aaa2  lea     rcx, [rbp+arg_0]
0x18001aaa6  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>>,std::_Iterator_base0>::operator++(void)
0x18001aaab  mov     rbx, [rbp+arg_0]
0x18001aaaf  jmp     short loc_18001AA88
0x18001aab1  lea     rcx, [rbp+var_20]
0x18001aab5  call    ??1?$shared_lock@Vshared_mutex@std@@@std@@QEAA@XZ; std::shared_lock<std::shared_mutex>::~shared_lock<std::shared_mutex>(void)
0x18001aaba  add     rsp, 78h
0x18001aabe  pop     rbx
0x18001aabf  pop     rbp
0x18001aac0  retn
```
