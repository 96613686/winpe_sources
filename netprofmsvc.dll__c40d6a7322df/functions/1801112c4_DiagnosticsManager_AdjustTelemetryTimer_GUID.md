# DiagnosticsManager::AdjustTelemetryTimer(_GUID)

- ea: `0x1801112c4`
- end: `0x18011146e`
- name: `?AdjustTelemetryTimer@DiagnosticsManager@@AEAAXU_GUID@@@Z`
- size: `426`
- prototype: `void __fastcall(PVOID pv, struct _GUID *__struct_ptr)`
- caller_count: `9`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x1800674f0`
- `0x18006773c`
- `0x180110240`
- `0x18011059c`
- `0x180110754`
- `0x1801108ac`
- `0x180110afc`
- `0x180110dc4`
- `0x180110f40`

## callees

- `0x180009990`
- `0x180048608`
- `0x1800704dc`
- `0x1800a88a0`
- `0x18010d750`
- `0x1801112c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180111317`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801113f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180111424`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180111464`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180111317`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801113f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180111424`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180111464`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180111413`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180111413`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18011139d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18011139d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1801112e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1801112e3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall DiagnosticsManager::AdjustTelemetryTimer(struct _TP_TIMER **pv, struct _GUID *a2)
{
  ULONGLONG TickCount64; // r14
  struct _TP_TIMER *i; // rcx
  __int128 v6; // xmm0
  struct _TP_TIMER *v7; // rdx
  const char *v8; // r9
  struct _TP_TIMER **v9; // rsi
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v11; // rcx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-58h] BYREF
  __int128 v13; // [rsp+28h] [rbp-50h] BYREF
  ULONGLONG v14; // [rsp+38h] [rbp-40h]
  struct _FILETIME pftDueTime; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  TickCount64 = GetTickCount64();
  lpCriticalSection = 0;
  wil::EnterCriticalSection(&lpCriticalSection, pv + 3);
  if ( *((_BYTE *)pv + 1232) )
  {
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
  }
  else
  {
    for ( i = pv[150]; i != pv[151]; i = (struct _TP_TIMER *)((char *)i + 24) )
    {
      if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)i && *(_QWORD *)a2->Data4 == *((_QWORD *)i + 1) )
        goto LABEL_12;
    }
    v6 = (__int128)*a2;
    v13 = (__int128)*a2;
    v14 = TickCount64;
    v7 = pv[151];
    if ( v7 == pv[152] )
    {
      try
      {
        std::vector<std::pair<_GUID,unsigned __int64>>::_Emplace_reallocate<std::pair<_GUID,unsigned __int64>>(
          pv + 150,
          v7,
          &v13);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0xA64,
          (unsigned int)"onecore\\net\\netprofiles\\service\\src\\networkdiagnostics\\lib\\diagnosticsmanager.cpp",
          v8);
        return;
      }
    }
    else
    {
      *(_OWORD *)v7 = v6;
      *((_QWORD *)v7 + 2) = TickCount64;
      pv[151] = (struct _TP_TIMER *)((char *)pv[151] + 24);
    }
LABEL_12:
    v9 = pv + 192;
    if ( !pv[192] )
    {
      ThreadpoolTimer = CreateThreadpoolTimer(DiagnosticsManager::TelemetryTimerCallback, pv, 0);
      wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        pv + 192,
        ThreadpoolTimer);
    }
    v11 = *v9;
    if ( *v9 )
    {
      if ( TickCount64 - *((_QWORD *)pv[150] + 2) <= 0xCD140 )
      {
        pftDueTime = (struct _FILETIME)-300000000LL;
        SetThreadpoolTimer(v11, &pftDueTime, 0, 0xBB8u);
        if ( lpCriticalSection )
          LeaveCriticalSection(lpCriticalSection);
      }
      else
      {
        *((_BYTE *)pv + 1233) = 1;
        if ( (unsigned int)dword_1801BD288 > 5 )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            v11,
            word_1801938C2);
        if ( lpCriticalSection )
          LeaveCriticalSection(lpCriticalSection);
      }
    }
    else
    {
      if ( (unsigned int)dword_1801BD288 > 5 )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          0,
          qword_180193868);
      if ( lpCriticalSection )
        LeaveCriticalSection(lpCriticalSection);
    }
  }
}

```

## disassembly

```asm
0x1801112c4  push    rbx
0x1801112c6  push    rsi
0x1801112c7  push    rdi
0x1801112c8  push    r14
0x1801112ca  sub     rsp, 58h
0x1801112ce  mov     rax, cs:__security_cookie
0x1801112d5  xor     rax, rsp
0x1801112d8  mov     [rsp+78h+var_30], rax
0x1801112dd  mov     rsi, rdx
0x1801112e0  mov     rbx, rcx
0x1801112e3  call    cs:__imp_GetTickCount64
0x1801112e9  mov     r14, rax
0x1801112ec  mov     [rsp+78h+lpCriticalSection], 0
0x1801112f5  lea     rdx, [rbx+18h]
0x1801112f9  lea     rcx, [rsp+78h+lpCriticalSection]
0x1801112fe  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180111303  nop
0x180111304  cmp     byte ptr [rbx+4D0h], 0
0x18011130b  jz      short loc_180111323
0x18011130d  mov     rcx, [rsp+78h+lpCriticalSection]; lpCriticalSection
0x180111312  test    rcx, rcx
0x180111315  jz      short loc_18011131E
0x180111317  call    cs:__imp_LeaveCriticalSection
0x18011131d  nop
0x18011131e  jmp     loc_18011142B
0x180111323  lea     rdi, [rbx+4B0h]
0x18011132a  mov     rcx, [rdi]
0x18011132d  mov     rdx, [rbx+4B8h]
0x180111334  jmp     short loc_18011134C
0x180111336  mov     rax, [rsi]
0x180111339  cmp     rax, [rcx]
0x18011133c  jnz     short loc_180111348
0x18011133e  mov     rax, [rsi+8]
0x180111342  cmp     rax, [rcx+8]
0x180111346  jz      short loc_180111383
0x180111348  add     rcx, 18h
0x18011134c  cmp     rcx, rdx
0x18011134f  jnz     short loc_180111336
0x180111351  movups  xmm0, xmmword ptr [rsi]
0x180111354  movups  [rsp+78h+var_50], xmm0
0x180111359  mov     [rsp+78h+var_40], r14
0x18011135e  mov     rdx, [rdi+8]
0x180111362  cmp     rdx, [rdi+10h]
0x180111366  jz      short loc_180111376
0x180111368  movups  xmmword ptr [rdx], xmm0
0x18011136b  mov     [rdx+10h], r14
0x18011136f  add     qword ptr [rdi+8], 18h
0x180111374  jmp     short loc_180111383
0x180111376  lea     r8, [rsp+78h+var_50]
0x18011137b  mov     rcx, rdi
0x18011137e  call    ??$_Emplace_reallocate@U?$pair@U_GUID@@_K@std@@@?$vector@U?$pair@U_GUID@@_K@std@@V?$allocator@U?$pair@U_GUID@@_K@std@@@2@@std@@AEAAPEAU?$pair@U_GUID@@_K@1@QEAU21@$$QEAU21@@Z; std::vector<std::pair<_GUID,unsigned __int64>>::_Emplace_reallocate<std::pair<_GUID,unsigned __int64>>(std::pair<_GUID,unsigned __int64> * const,std::pair<_GUID,unsigned __int64> &&)
0x180111383  lea     rsi, [rbx+600h]
0x18011138a  cmp     qword ptr [rsi], 0
0x18011138e  jnz     short loc_1801113AE
0x180111390  xor     r8d, r8d; pcbe
0x180111393  mov     rdx, rbx; pv
0x180111396  lea     rcx, ?TelemetryTimerCallback@DiagnosticsManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18011139d  call    cs:__imp_CreateThreadpoolTimer
0x1801113a3  mov     rdx, rax
0x1801113a6  mov     rcx, rsi
0x1801113a9  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1801113ae  mov     rcx, [rsi]; pti
0x1801113b1  test    rcx, rcx
0x1801113b4  jz      loc_180111442
0x1801113ba  mov     rax, [rdi]
0x1801113bd  sub     r14, [rax+10h]
0x1801113c1  cmp     r14, 0CD140h
0x1801113c8  jbe     short loc_1801113FC
0x1801113ca  mov     byte ptr [rbx+4D1h], 1
0x1801113d1  mov     eax, cs:dword_1801BD288
0x1801113d7  cmp     eax, 5
0x1801113da  jbe     short loc_1801113E9
0x1801113dc  lea     rdx, word_1801938C2
0x1801113e3  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801113e8  nop
0x1801113e9  mov     rcx, [rsp+78h+lpCriticalSection]; lpCriticalSection
0x1801113ee  test    rcx, rcx
0x1801113f1  jz      short loc_1801113FA
0x1801113f3  call    cs:__imp_LeaveCriticalSection
0x1801113f9  nop
0x1801113fa  jmp     short loc_18011142B
0x1801113fc  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFEE1E5D00h
0x180111405  mov     r9d, 0BB8h; msWindowLength
0x18011140b  xor     r8d, r8d; msPeriod
0x18011140e  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x180111413  call    cs:__imp_SetThreadpoolTimer
0x180111419  nop
0x18011141a  mov     rcx, [rsp+78h+lpCriticalSection]; lpCriticalSection
0x18011141f  test    rcx, rcx
0x180111422  jz      short loc_18011142B
0x180111424  call    cs:__imp_LeaveCriticalSection
0x18011142a  nop
0x18011142b  mov     rcx, [rsp+78h+var_30]
0x180111430  xor     rcx, rsp; StackCookie
0x180111433  call    __security_check_cookie
0x180111438  add     rsp, 58h
0x18011143c  pop     r14
0x18011143e  pop     rdi
0x18011143f  pop     rsi
0x180111440  pop     rbx
0x180111441  retn
0x180111442  mov     eax, cs:dword_1801BD288
0x180111448  cmp     eax, 5
0x18011144b  jbe     short loc_18011145A
0x18011144d  lea     rdx, qword_180193868
0x180111454  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180111459  nop
0x18011145a  mov     rcx, [rsp+78h+lpCriticalSection]; lpCriticalSection
0x18011145f  test    rcx, rcx
0x180111462  jz      short loc_18011146B
0x180111464  call    cs:__imp_LeaveCriticalSection
0x18011146a  nop
0x18011146b  jmp     short loc_18011142B
```
