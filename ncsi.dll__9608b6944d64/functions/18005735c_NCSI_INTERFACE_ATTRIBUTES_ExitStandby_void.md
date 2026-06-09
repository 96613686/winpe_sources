# NCSI_INTERFACE_ATTRIBUTES::ExitStandby(void)

- ea: `0x18005735c`
- end: `0x1800576ab`
- name: `?ExitStandby@NCSI_INTERFACE_ATTRIBUTES@@QEAAXXZ`
- size: `847`
- prototype: `void __fastcall(NCSI_INTERFACE_ATTRIBUTES *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update`

## callers

- `0x18002318c`

## callees

- `0x1800044f0`
- `0x1800045a0`
- `0x18000e350`
- `0x18001c698`
- `0x180021d28`
- `0x180021e64`
- `0x18002e6d0`
- `0x18002e960`
- `0x1800301e8`
- `0x180047240`
- `0x18004a110`
- `0x180055a68`
- `0x180055f34`
- `0x18005735c`
- `0x180059e0c`
- `0x180062ca8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800573f0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800573f0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005748f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005748f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800575ac`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800575ac`

## pseudocode

```c
void __fastcall NCSI_INTERFACE_ATTRIBUTES::ExitStandby(NCSI_INTERFACE_ATTRIBUTES *this)
{
  NCSI_INTERFACE_ATTRIBUTES *v1; // r15
  NCSI_INTERFACE_ATTRIBUTES *v2; // rdi
  __int64 v3; // rcx
  PTP_TIMER *v4; // r14
  void **v5; // rax
  PTP_TIMER ThreadpoolTimer; // rax
  const char *v7; // r9
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  NCSI_INTERFACE_ATTRIBUTES *v14; // rcx
  __int64 v15; // r8
  __int64 v16; // [rsp+50h] [rbp-48h] BYREF
  NCSI_INTERFACE_ATTRIBUTES *v17; // [rsp+58h] [rbp-40h] BYREF
  struct _FILETIME v18; // [rsp+60h] [rbp-38h] BYREF
  __int64 v19; // [rsp+68h] [rbp-30h] BYREF
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v1 = this;
  v2 = this;
  v17 = this;
  if ( (unsigned __int8)NCSI_INTERFACE_ATTRIBUTES::IsBehindHotspot(this, 0)
    || (unsigned __int8)NCSI_INTERFACE_ATTRIBUTES::IsBehindHotspot(v3, 1) )
  {
    v4 = (PTP_TIMER *)(v3 + 12848);
    v18 = (struct _FILETIME)(v3 + 12848);
    if ( *(_QWORD *)(v3 + 12848) )
      goto LABEL_6;
    try
    {
      v5 = (void **)std::make_unique<_NET_LUID_LH,_NET_LUID_LH &,0>(&pftDueTime, v1);
      std::unique_ptr<_NET_LUID_LH>::operator=<std::default_delete<_NET_LUID_LH>,0>((void **)v1 + 1605, v5);
      std::unique_ptr<_NET_LUID_LH>::~unique_ptr<_NET_LUID_LH>(&pftDueTime);
      ThreadpoolTimer = CreateThreadpoolTimer(
                          NCSI_INTERFACE_ATTRIBUTES::NcsiCaptivePortalTimerExpireCallback,
                          *((PVOID *)v1 + 1605),
                          0);
      wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        v4,
        ThreadpoolTimer);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x914,
        (unsigned int)"onecore\\net\\diagnostics\\ncsi\\lib\\interfaceattributes.cpp",
        v7);
      v2 = v17;
      v1 = v17;
      v4 = (PTP_TIMER *)v18;
    }
    if ( *v4 )
    {
LABEL_6:
      if ( (unsigned int)dword_18009A080 > 5 )
      {
        LODWORD(v16) = 0;
        LODWORD(v17) = NCSI_INTERFACE_ATTRIBUTES::GetIfaceType(v2);
        v18 = *(struct _FILETIME *)v1;
        v19 = (__int64)v2 + 8;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v8,
          (int)&unk_180087270,
          v9,
          v10,
          &v19,
          (__int64)&v18,
          (__int64)&v17,
          (__int64)&v16);
      }
      pftDueTime = 0;
      SetThreadpoolTimer(*v4, &pftDueTime, 0, 0);
    }
    if ( (unsigned int)dword_18009A048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18009A048, 0x200000000000LL) )
    {
      v19 = 2048;
      v18 = (struct _FILETIME)*((unsigned int *)v2 + 3214);
      LODWORD(v17) = *((unsigned __int16 *)v1 + 3);
      pftDueTime = *(struct _FILETIME *)v1;
      v16 = (__int64)v2 + 8;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        v11,
        (int)&byte_1800871F7,
        v12,
        v13,
        &v16,
        (__int64)&pftDueTime,
        (__int64)&v17,
        (__int64)&v18,
        (__int64)&v19);
    }
  }
  NCSI_INTERFACE_ATTRIBUTES::PROBE_RETRY_STATE::UpdateExitingStandby((NCSI_INTERFACE_ATTRIBUTES *)((char *)v2 + 4540));
  NCSI_INTERFACE_ATTRIBUTES::PROBE_RETRY_STATE::UpdateExitingStandby((NCSI_INTERFACE_ATTRIBUTES *)((char *)v2 + 8484));
  NCSI_INTERFACE_ATTRIBUTES::PROBE_RETRY_STATE::UpdateExitingStandby((NCSI_INTERFACE_ATTRIBUTES *)((char *)v2 + 4556));
  NCSI_INTERFACE_ATTRIBUTES::PROBE_RETRY_STATE::UpdateExitingStandby((NCSI_INTERFACE_ATTRIBUTES *)((char *)v2 + 8500));
  InterfaceIpFamilyCounters::UpdatePowerState((char *)v2 + 11912, 1);
  InterfaceIpFamilyCounters::UpdatePowerState((char *)v2 + 12000, 1);
  if ( *((_BYTE *)v2 + 7696) )
  {
    ActiveProbeManager::TryNcsiQueueActiveInternetProbe(v2, 12);
    *((_BYTE *)v2 + 7696) = 0;
    if ( !*((_BYTE *)v2 + 11640) )
      return;
    goto LABEL_26;
  }
  if ( *((_BYTE *)v2 + 11640) )
  {
LABEL_26:
    ActiveProbeManager::TryNcsiQueueActiveInternetProbe(v2, 12);
    *((_BYTE *)v2 + 11640) = 0;
    return;
  }
  if ( *((_BYTE *)v2 + 7697) )
  {
    ActiveProbeManager::TryNcsiQueueActiveInternetProbe(v2, 13);
    *((_BYTE *)v2 + 7697) = 0;
    if ( !*((_BYTE *)v2 + 11641) )
      return;
    goto LABEL_24;
  }
  if ( *((_BYTE *)v2 + 11641) )
  {
LABEL_24:
    ActiveProbeManager::TryNcsiQueueActiveInternetProbe(v2, 13);
    *((_BYTE *)v2 + 11641) = 0;
    return;
  }
  if ( GetTickCount64() - *((_QWORD *)v2 + 1609) > 0x1388 )
  {
    if ( NCSI_INTERFACE_ATTRIBUTES::GetIfaceType(v2) == 71 || NCSI_INTERFACE_ATTRIBUTES::GetIfaceType(v14) == 6 )
    {
      LOBYTE(v15) = 1;
      NCSI_INTERFACE_ATTRIBUTES::StartBasicConnectivityCheck(v2, 0, v15, 0);
    }
    if ( !*((_DWORD *)v2 + 6) )
    {
      _m_prefetchw((char *)v2 + 32);
      if ( !_InterlockedOr((volatile signed __int32 *)v2 + 8, 0) )
        NCSI_INTERFACE_ATTRIBUTES::ScheduleNextCorpLocationProbe(v2);
    }
  }
}

```

## disassembly

```asm
0x18005735c  mov     [rsp+arg_8], rbx
0x180057361  mov     [rsp+arg_10], rsi
0x180057366  push    rdi
0x180057367  push    r14
0x180057369  push    r15
0x18005736b  sub     rsp, 80h
0x180057372  mov     rax, cs:__security_cookie
0x180057379  xor     rax, rsp
0x18005737c  mov     [rsp+98h+var_20], rax
0x180057381  mov     r15, rcx
0x180057384  mov     rdi, rcx
0x180057387  mov     [rsp+98h+var_40], rcx
0x18005738c  xor     edx, edx
0x18005738e  call    ?IsBehindHotspot@NCSI_INTERFACE_ATTRIBUTES@@QEBA_NW4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::IsBehindHotspot(_NLA_CONNECTIVITY_FAMILY)
0x180057393  xor     esi, esi
0x180057395  test    al, al
0x180057397  jnz     short loc_1800573A9
0x180057399  lea     edx, [rsi+1]
0x18005739c  call    ?IsBehindHotspot@NCSI_INTERFACE_ATTRIBUTES@@QEBA_NW4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::IsBehindHotspot(_NLA_CONNECTIVITY_FAMILY)
0x1800573a1  test    al, al
0x1800573a3  jz      loc_18005752A
0x1800573a9  lea     r14, [rcx+3230h]
0x1800573b0  mov     [rsp+98h+var_38], r14
0x1800573b5  cmp     [r14], rsi
0x1800573b8  jnz     short loc_180057418
0x1800573ba  mov     rdx, r15
0x1800573bd  lea     rcx, [rsp+98h+pftDueTime]
0x1800573c2  call    ??$make_unique@T_NET_LUID_LH@@AEAT1@$0A@@std@@YA?AV?$unique_ptr@T_NET_LUID_LH@@U?$default_delete@T_NET_LUID_LH@@@std@@@0@AEAT_NET_LUID_LH@@@Z; std::make_unique<_NET_LUID_LH,_NET_LUID_LH &,0>(_NET_LUID_LH &)
0x1800573c7  lea     rbx, [r15+3228h]
0x1800573ce  mov     rdx, rax
0x1800573d1  mov     rcx, rbx
0x1800573d4  call    ??$?4U?$default_delete@T_NET_LUID_LH@@@std@@$0A@@?$unique_ptr@T_NET_LUID_LH@@U?$default_delete@T_NET_LUID_LH@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<_NET_LUID_LH>::operator=<std::default_delete<_NET_LUID_LH>,0>(std::unique_ptr<_NET_LUID_LH> &&)
0x1800573d9  lea     rcx, [rsp+98h+pftDueTime]
0x1800573de  call    ??1?$unique_ptr@T_NET_LUID_LH@@U?$default_delete@T_NET_LUID_LH@@@std@@@std@@QEAA@XZ; std::unique_ptr<_NET_LUID_LH>::~unique_ptr<_NET_LUID_LH>(void)
0x1800573e3  xor     r8d, r8d; pcbe
0x1800573e6  mov     rdx, [rbx]; pv
0x1800573e9  lea     rcx, ?NcsiCaptivePortalTimerExpireCallback@NCSI_INTERFACE_ATTRIBUTES@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800573f0  call    cs:__imp_CreateThreadpoolTimer
0x1800573f6  mov     rdx, rax
0x1800573f9  mov     rcx, r14
0x1800573fc  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180057401  nop
0x180057402  jmp     short loc_180057413
0x180057404  xor     esi, esi
0x180057406  mov     rdi, [rsp+98h+var_40]
0x18005740b  mov     r15, rdi
0x18005740e  mov     r14, [rsp+98h+var_38]
0x180057413  cmp     [r14], rsi
0x180057416  jz      short loc_180057495
0x180057418  mov     eax, cs:dword_18009A080
0x18005741e  cmp     eax, 5
0x180057421  jbe     short loc_180057478
0x180057423  mov     dword ptr [rsp+98h+var_48], esi
0x180057427  mov     rcx, rdi; this
0x18005742a  call    ?GetIfaceType@NCSI_INTERFACE_ATTRIBUTES@@QEBA?BKXZ; NCSI_INTERFACE_ATTRIBUTES::GetIfaceType(void)
0x18005742f  mov     dword ptr [rsp+98h+var_40], eax
0x180057433  mov     rax, [r15]
0x180057436  mov     [rsp+98h+var_38], rax
0x18005743b  lea     rax, [rdi+8]
0x18005743f  mov     [rsp+98h+var_30], rax
0x180057444  lea     rax, [rsp+98h+var_48]
0x180057449  mov     [rsp+98h+var_60], rax
0x18005744e  lea     rax, [rsp+98h+var_40]
0x180057453  mov     [rsp+98h+var_68], rax
0x180057458  lea     rax, [rsp+98h+var_38]
0x18005745d  mov     [rsp+98h+var_70], rax
0x180057462  lea     rax, [rsp+98h+var_30]
0x180057467  mov     [rsp+98h+var_78], rax
0x18005746c  lea     rdx, unk_180087270
0x180057473  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180057478  mov     qword ptr [rsp+98h+pftDueTime.dwLowDateTime], 0
0x180057481  xor     r9d, r9d; msWindowLength
0x180057484  xor     r8d, r8d; msPeriod
0x180057487  lea     rdx, [rsp+98h+pftDueTime]; pftDueTime
0x18005748c  mov     rcx, [r14]; pti
0x18005748f  call    cs:__imp_SetThreadpoolTimer
0x180057495  mov     eax, cs:dword_18009A048
0x18005749b  cmp     eax, 5
0x18005749e  jbe     loc_18005752A
0x1800574a4  mov     rdx, 200000000000h
0x1800574ae  lea     rcx, dword_18009A048
0x1800574b5  call    _tlgKeywordOn
0x1800574ba  test    al, al
0x1800574bc  jz      short loc_18005752A
0x1800574be  mov     [rsp+98h+var_30], 800h
0x1800574c7  mov     eax, [rdi+3238h]
0x1800574cd  mov     [rsp+98h+var_38], rax
0x1800574d2  movzx   eax, word ptr [r15+6]
0x1800574d7  mov     dword ptr [rsp+98h+var_40], eax
0x1800574db  mov     rax, [r15]
0x1800574de  mov     qword ptr [rsp+98h+pftDueTime.dwLowDateTime], rax
0x1800574e3  lea     rax, [rdi+8]
0x1800574e7  mov     [rsp+98h+var_48], rax
0x1800574ec  lea     rax, [rsp+98h+var_30]
0x1800574f1  mov     [rsp+98h+var_58], rax
0x1800574f6  lea     rax, [rsp+98h+var_38]
0x1800574fb  mov     [rsp+98h+var_60], rax
0x180057500  lea     rax, [rsp+98h+var_40]
0x180057505  mov     [rsp+98h+var_68], rax
0x18005750a  lea     rax, [rsp+98h+pftDueTime]
0x18005750f  mov     [rsp+98h+var_70], rax
0x180057514  lea     rax, [rsp+98h+var_48]
0x180057519  mov     [rsp+98h+var_78], rax
0x18005751e  lea     rdx, byte_1800871F7
0x180057525  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18005752a  lea     rcx, [rdi+11BCh]; this
0x180057531  call    ?UpdateExitingStandby@PROBE_RETRY_STATE@NCSI_INTERFACE_ATTRIBUTES@@QEAAXXZ; NCSI_INTERFACE_ATTRIBUTES::PROBE_RETRY_STATE::UpdateExitingStandby(void)
0x180057536  lea     rcx, [rdi+2124h]; this
0x18005753d  call    ?UpdateExitingStandby@PROBE_RETRY_STATE@NCSI_INTERFACE_ATTRIBUTES@@QEAAXXZ; NCSI_INTERFACE_ATTRIBUTES::PROBE_RETRY_STATE::UpdateExitingStandby(void)
0x180057542  lea     rcx, [rdi+11CCh]; this
0x180057549  call    ?UpdateExitingStandby@PROBE_RETRY_STATE@NCSI_INTERFACE_ATTRIBUTES@@QEAAXXZ; NCSI_INTERFACE_ATTRIBUTES::PROBE_RETRY_STATE::UpdateExitingStandby(void)
0x18005754e  lea     rcx, [rdi+2134h]; this
0x180057555  call    ?UpdateExitingStandby@PROBE_RETRY_STATE@NCSI_INTERFACE_ATTRIBUTES@@QEAAXXZ; NCSI_INTERFACE_ATTRIBUTES::PROBE_RETRY_STATE::UpdateExitingStandby(void)
0x18005755a  lea     rcx, [rdi+2E88h]
0x180057561  mov     edx, 1
0x180057566  call    ?UpdatePowerState@InterfaceIpFamilyCounters@@QEAAXW4PowerState@Power@Ncsi@@@Z; InterfaceIpFamilyCounters::UpdatePowerState(Ncsi::Power::PowerState)
0x18005756b  lea     rcx, [rdi+2EE0h]
0x180057572  mov     edx, 1
0x180057577  call    ?UpdatePowerState@InterfaceIpFamilyCounters@@QEAAXW4PowerState@Power@Ncsi@@@Z; InterfaceIpFamilyCounters::UpdatePowerState(Ncsi::Power::PowerState)
0x18005757c  cmp     [rdi+1E10h], sil
0x180057583  jnz     loc_18005764E
0x180057589  cmp     [rdi+2D78h], sil
0x180057590  jnz     loc_18005766D
0x180057596  cmp     [rdi+1E11h], sil
0x18005759d  jnz     short loc_180057615
0x18005759f  cmp     [rdi+2D79h], sil
0x1800575a6  jnz     loc_180057634
0x1800575ac  call    cs:__imp_GetTickCount64
0x1800575b2  sub     rax, [rdi+3248h]
0x1800575b9  cmp     rax, 1388h
0x1800575bf  jbe     loc_180057685
0x1800575c5  mov     rcx, rdi; this
0x1800575c8  call    ?GetIfaceType@NCSI_INTERFACE_ATTRIBUTES@@QEBA?BKXZ; NCSI_INTERFACE_ATTRIBUTES::GetIfaceType(void)
0x1800575cd  cmp     eax, 47h ; 'G'
0x1800575d0  jz      short loc_1800575DC
0x1800575d2  call    ?GetIfaceType@NCSI_INTERFACE_ATTRIBUTES@@QEBA?BKXZ; NCSI_INTERFACE_ATTRIBUTES::GetIfaceType(void)
0x1800575d7  cmp     eax, 6
0x1800575da  jnz     short loc_1800575EC
0x1800575dc  xor     r9d, r9d
0x1800575df  mov     r8b, 1
0x1800575e2  xor     edx, edx
0x1800575e4  mov     rcx, rdi
0x1800575e7  call    ?StartBasicConnectivityCheck@NCSI_INTERFACE_ATTRIBUTES@@QEAAXW4_NLA_CONNECTIVITY_FAMILY@@_NW4BasicConnectivityCheckReason@@@Z; NCSI_INTERFACE_ATTRIBUTES::StartBasicConnectivityCheck(_NLA_CONNECTIVITY_FAMILY,bool,BasicConnectivityCheckReason)
0x1800575ec  cmp     [rdi+18h], esi
0x1800575ef  jnz     loc_180057685
0x1800575f5  prefetchw byte ptr [rdi+20h]
0x1800575f9  mov     eax, [rdi+20h]
0x1800575fc  mov     edx, eax
0x1800575fe  or      edx, esi
0x180057600  lock cmpxchg [rdi+20h], edx
0x180057605  jnz     short loc_1800575FC
0x180057607  test    eax, eax
0x180057609  jnz     short loc_180057685
0x18005760b  mov     rcx, rdi; this
0x18005760e  call    ?ScheduleNextCorpLocationProbe@NCSI_INTERFACE_ATTRIBUTES@@QEAAXXZ; NCSI_INTERFACE_ATTRIBUTES::ScheduleNextCorpLocationProbe(void)
0x180057613  jmp     short loc_180057685
0x180057615  xor     r8d, r8d
0x180057618  lea     edx, [r8+0Dh]
0x18005761c  mov     rcx, rdi
0x18005761f  call    ?TryNcsiQueueActiveInternetProbe@ActiveProbeManager@@SA?AW4ActiveProbeQueueResult@@PEAVNCSI_INTERFACE_ATTRIBUTES@@W4NcsiProbePerformReason@@W4_NLA_CONNECTIVITY_FAMILY@@@Z; ActiveProbeManager::TryNcsiQueueActiveInternetProbe(NCSI_INTERFACE_ATTRIBUTES *,NcsiProbePerformReason,_NLA_CONNECTIVITY_FAMILY)
0x180057624  mov     [rdi+1E11h], sil
0x18005762b  cmp     [rdi+2D79h], sil
0x180057632  jz      short loc_180057685
0x180057634  mov     edx, 0Dh
0x180057639  lea     r8d, [rdx-0Ch]
0x18005763d  mov     rcx, rdi
0x180057640  call    ?TryNcsiQueueActiveInternetProbe@ActiveProbeManager@@SA?AW4ActiveProbeQueueResult@@PEAVNCSI_INTERFACE_ATTRIBUTES@@W4NcsiProbePerformReason@@W4_NLA_CONNECTIVITY_FAMILY@@@Z; ActiveProbeManager::TryNcsiQueueActiveInternetProbe(NCSI_INTERFACE_ATTRIBUTES *,NcsiProbePerformReason,_NLA_CONNECTIVITY_FAMILY)
0x180057645  mov     [rdi+2D79h], sil
0x18005764c  jmp     short loc_180057685
0x18005764e  xor     r8d, r8d
0x180057651  lea     edx, [r8+0Ch]
0x180057655  mov     rcx, rdi
0x180057658  call    ?TryNcsiQueueActiveInternetProbe@ActiveProbeManager@@SA?AW4ActiveProbeQueueResult@@PEAVNCSI_INTERFACE_ATTRIBUTES@@W4NcsiProbePerformReason@@W4_NLA_CONNECTIVITY_FAMILY@@@Z; ActiveProbeManager::TryNcsiQueueActiveInternetProbe(NCSI_INTERFACE_ATTRIBUTES *,NcsiProbePerformReason,_NLA_CONNECTIVITY_FAMILY)
0x18005765d  mov     [rdi+1E10h], sil
0x180057664  cmp     [rdi+2D78h], sil
0x18005766b  jz      short loc_180057685
0x18005766d  mov     edx, 0Ch
0x180057672  lea     r8d, [rdx-0Bh]
0x180057676  mov     rcx, rdi
0x180057679  call    ?TryNcsiQueueActiveInternetProbe@ActiveProbeManager@@SA?AW4ActiveProbeQueueResult@@PEAVNCSI_INTERFACE_ATTRIBUTES@@W4NcsiProbePerformReason@@W4_NLA_CONNECTIVITY_FAMILY@@@Z; ActiveProbeManager::TryNcsiQueueActiveInternetProbe(NCSI_INTERFACE_ATTRIBUTES *,NcsiProbePerformReason,_NLA_CONNECTIVITY_FAMILY)
0x18005767e  mov     [rdi+2D78h], sil
0x180057685  mov     rcx, [rsp+98h+var_20]
0x18005768a  xor     rcx, rsp; StackCookie
0x18005768d  call    __security_check_cookie
0x180057692  lea     r11, [rsp+98h+var_18]
0x18005769a  mov     rbx, [r11+28h]
0x18005769e  mov     rsi, [r11+30h]
0x1800576a2  mov     rsp, r11
0x1800576a5  pop     r15
0x1800576a7  pop     r14
0x1800576a9  pop     rdi
0x1800576aa  retn
```
