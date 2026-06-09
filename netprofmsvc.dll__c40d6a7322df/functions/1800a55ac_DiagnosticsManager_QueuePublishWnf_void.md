# DiagnosticsManager::QueuePublishWnf(void)

- ea: `0x1800a55ac`
- end: `0x1800a5701`
- name: `?QueuePublishWnf@DiagnosticsManager@@AEAAXXZ`
- size: `341`
- prototype: `void __fastcall(DiagnosticsManager *__hidden this)`
- caller_count: `5`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18002bf08`
- `0x1800a530c`
- `0x1800a53b4`
- `0x1801108ac`
- `0x180110dc4`

## callees

- `0x180009990`
- `0x180048608`
- `0x18005fb58`
- `0x1800704dc`
- `0x180095f2c`
- `0x1800a55ac`
- `0x1800a88a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a5676`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a56b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a56e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a5676`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a56b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a56e2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800a56d1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800a56d1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800a5628`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800a5628`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800a55f7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800a55f7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall DiagnosticsManager::QueuePublishWnf(DiagnosticsManager *this)
{
  const struct _WNF_STATE_NAME *v2; // rdx
  const char *v3; // r9
  ULONGLONG TickCount64; // rax
  __int64 v5; // r8
  ULONGLONG v6; // rdi
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v8; // rcx
  __int64 v9; // rcx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-28h] BYREF
  struct _FILETIME pftDueTime; // [rsp+28h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  lpCriticalSection = 0;
  wil::EnterCriticalSection(&lpCriticalSection, (char *)this + 24);
  try
  {
    if ( *((_BYTE *)this + 8) )
    {
      wil::wnf_publish((wil *)&WNF_NLM_NETWORK_STATE_DIAGNOSTICS, v2);
      goto LABEL_22;
    }
    TickCount64 = GetTickCount64();
    v6 = TickCount64;
    if ( !*((_QWORD *)this + 153) )
      *((_QWORD *)this + 153) = TickCount64;
    if ( !*(_QWORD *)this )
    {
      ThreadpoolTimer = CreateThreadpoolTimer(
                          DiagnosticsManager::OnWnfDebounceTimerFired,
                          DiagnosticsManager::s_singleInstance,
                          0);
      wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        this,
        ThreadpoolTimer);
    }
    v8 = *(struct _TP_TIMER **)this;
    if ( *(_QWORD *)this )
    {
      if ( v6 - *((_QWORD *)this + 153) <= 0x3E8 )
      {
        pftDueTime = (struct _FILETIME)-1000000LL;
        SetThreadpoolTimer(v8, &pftDueTime, 0, 0x64u);
LABEL_22:
        if ( lpCriticalSection )
          LeaveCriticalSection(lpCriticalSection);
        return;
      }
      if ( (unsigned int)dword_1801BD288 > 5 )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          v8,
          &byte_1801937EF);
      if ( lpCriticalSection )
        LeaveCriticalSection(lpCriticalSection);
    }
    else
    {
      if ( (unsigned int)dword_1801BD288 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1801BD288, 2, v5) )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          v9,
          byte_1801939E1);
      if ( lpCriticalSection )
        LeaveCriticalSection(lpCriticalSection);
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xAAF,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\networkdiagnostics\\lib\\diagnosticsmanager.cpp",
      v3);
  }
}

```

## disassembly

```asm
0x1800a55ac  mov     [rsp+arg_8], rbx
0x1800a55b1  push    rdi
0x1800a55b2  sub     rsp, 40h
0x1800a55b6  mov     rax, cs:__security_cookie
0x1800a55bd  xor     rax, rsp
0x1800a55c0  mov     [rsp+48h+var_18], rax
0x1800a55c5  mov     rbx, rcx
0x1800a55c8  mov     [rsp+48h+lpCriticalSection], 0
0x1800a55d1  lea     rdx, [rcx+18h]
0x1800a55d5  lea     rcx, [rsp+48h+lpCriticalSection]
0x1800a55da  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800a55df  nop
0x1800a55e0  cmp     byte ptr [rbx+8], 0
0x1800a55e4  jz      short loc_1800A55F7
0x1800a55e6  lea     rcx, WNF_NLM_NETWORK_STATE_DIAGNOSTICS; this
0x1800a55ed  call    ?wnf_publish@wil@@YAXAEBU_WNF_STATE_NAME@@@Z; wil::wnf_publish(_WNF_STATE_NAME const &)
0x1800a55f2  jmp     loc_1800A56D8
0x1800a55f7  call    cs:__imp_GetTickCount64
0x1800a55fd  mov     rdi, rax
0x1800a5600  cmp     qword ptr [rbx+4C8h], 0
0x1800a5608  jnz     short loc_1800A5611
0x1800a560a  mov     [rbx+4C8h], rax
0x1800a5611  cmp     qword ptr [rbx], 0
0x1800a5615  jnz     short loc_1800A5639
0x1800a5617  xor     r8d, r8d; pcbe
0x1800a561a  mov     rdx, cs:?s_singleInstance@DiagnosticsManager@@0V?$shared_ptr@VDiagnosticsManager@@@std@@A; pv
0x1800a5621  lea     rcx, ?OnWnfDebounceTimerFired@DiagnosticsManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800a5628  call    cs:__imp_CreateThreadpoolTimer
0x1800a562e  mov     rdx, rax
0x1800a5631  mov     rcx, rbx
0x1800a5634  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800a5639  mov     rcx, [rbx]; pti
0x1800a563c  test    rcx, rcx
0x1800a563f  jnz     short loc_1800A567F
0x1800a5641  mov     eax, cs:dword_1801BD288
0x1800a5647  cmp     eax, 5
0x1800a564a  jbe     short loc_1800A566C
0x1800a564c  lea     edx, [rcx+2]
0x1800a564f  lea     rcx, dword_1801BD288
0x1800a5656  call    _tlgKeywordOn
0x1800a565b  test    al, al
0x1800a565d  jz      short loc_1800A566C
0x1800a565f  lea     rdx, byte_1801939E1
0x1800a5666  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800a566b  nop
0x1800a566c  mov     rcx, [rsp+48h+lpCriticalSection]; lpCriticalSection
0x1800a5671  test    rcx, rcx
0x1800a5674  jz      short loc_1800A567D
0x1800a5676  call    cs:__imp_LeaveCriticalSection
0x1800a567c  nop
0x1800a567d  jmp     short loc_1800A56E9
0x1800a567f  sub     rdi, [rbx+4C8h]
0x1800a5686  cmp     rdi, 3E8h
0x1800a568d  jbe     short loc_1800A56BA
0x1800a568f  mov     eax, cs:dword_1801BD288
0x1800a5695  cmp     eax, 5
0x1800a5698  jbe     short loc_1800A56A7
0x1800a569a  lea     rdx, byte_1801937EF
0x1800a56a1  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800a56a6  nop
0x1800a56a7  mov     rcx, [rsp+48h+lpCriticalSection]; lpCriticalSection
0x1800a56ac  test    rcx, rcx
0x1800a56af  jz      short loc_1800A56B8
0x1800a56b1  call    cs:__imp_LeaveCriticalSection
0x1800a56b7  nop
0x1800a56b8  jmp     short loc_1800A56E9
0x1800a56ba  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0FFFFFFFFFFF0BDC0h
0x1800a56c3  mov     r9d, 64h ; 'd'; msWindowLength
0x1800a56c9  xor     r8d, r8d; msPeriod
0x1800a56cc  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x1800a56d1  call    cs:__imp_SetThreadpoolTimer
0x1800a56d7  nop
0x1800a56d8  mov     rcx, [rsp+48h+lpCriticalSection]; lpCriticalSection
0x1800a56dd  test    rcx, rcx
0x1800a56e0  jz      short loc_1800A56E9
0x1800a56e2  call    cs:__imp_LeaveCriticalSection
0x1800a56e8  nop
0x1800a56e9  mov     rcx, [rsp+48h+var_18]
0x1800a56ee  xor     rcx, rsp; StackCookie
0x1800a56f1  call    __security_check_cookie
0x1800a56f6  mov     rbx, [rsp+48h+arg_8]
0x1800a56fb  add     rsp, 40h
0x1800a56ff  pop     rdi
0x1800a5700  retn
```
