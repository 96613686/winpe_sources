# WorkThreadManager::s_EnsureFloodingListWatchdogUnderLock(void)

- ea: `0x18000bd6c`
- end: `0x18000bdd9`
- name: `?s_EnsureFloodingListWatchdogUnderLock@WorkThreadManager@@CAXXZ`
- size: `109`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180032958`
- `0x180032b10`

## callees

- `0x18000bd6c`
- `0x18000c0dc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000bd88`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000bd88`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000bdce`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000bdce`

## pseudocode

```c
void WorkThreadManager::s_EnsureFloodingListWatchdogUnderLock(void)
{
  struct _TP_TIMER *v0; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  v0 = WorkThreadManager::s_floodListTimer;
  if ( WorkThreadManager::s_floodListTimer
    || (ThreadpoolTimer = CreateThreadpoolTimer(WorkThreadManager::s_CheckFloodListProgress, 0, 0),
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          &WorkThreadManager::s_floodListTimer,
          ThreadpoolTimer),
        (v0 = WorkThreadManager::s_floodListTimer) != 0) )
  {
    pftDueTime = (struct _FILETIME)-250000LL;
    WorkThreadManager::s_anyThreadMadeProgress = 0;
    SetThreadpoolTimer(v0, &pftDueTime, 0, 0);
  }
}

```

## disassembly

```asm
0x18000bd6c  sub     rsp, 28h
0x18000bd70  mov     rcx, cs:?s_floodListTimer@WorkThreadManager@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> WorkThreadManager::s_floodListTimer
0x18000bd77  test    rcx, rcx
0x18000bd7a  jnz     short loc_18000BDA9
0x18000bd7c  xor     r8d, r8d; pcbe
0x18000bd7f  lea     rcx, ?s_CheckFloodListProgress@WorkThreadManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000bd86  xor     edx, edx; pv
0x18000bd88  call    cs:__imp_CreateThreadpoolTimer
0x18000bd8e  mov     rdx, rax
0x18000bd91  lea     rcx, ?s_floodListTimer@WorkThreadManager@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> WorkThreadManager::s_floodListTimer
0x18000bd98  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000bd9d  mov     rcx, cs:?s_floodListTimer@WorkThreadManager@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; pti
0x18000bda4  test    rcx, rcx
0x18000bda7  jz      short loc_18000BDD4
0x18000bda9  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], 0FFFFFFFFFFFC2F70h
0x18000bdb2  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18000bdb7  mov     rax, qword ptr [rsp+28h+pftDueTime.dwLowDateTime]
0x18000bdbc  xor     r9d, r9d; msWindowLength
0x18000bdbf  xor     r8d, r8d; msPeriod
0x18000bdc2  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x18000bdc7  mov     cs:?s_anyThreadMadeProgress@WorkThreadManager@@0_NA, 0; bool WorkThreadManager::s_anyThreadMadeProgress
0x18000bdce  call    cs:__imp_SetThreadpoolTimer
0x18000bdd4  add     rsp, 28h
0x18000bdd8  retn
```
