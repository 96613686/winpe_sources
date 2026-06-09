# DAS::Dispatcher::Dispatch::DispatchWorkCallback(_TP_CALLBACK_INSTANCE *,void *)

- ea: `0x180026cf0`
- end: `0x180026e24`
- name: `?DispatchWorkCallback@Dispatch@Dispatcher@DAS@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z`
- size: `308`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callees

- `0x18001dfe0`
- `0x18001ed54`
- `0x18002148c`
- `0x180023890`
- `0x18002394c`
- `0x18002410c`
- `0x180026cf0`
- `0x180034c00`
- `0x1800360f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180026d9c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180026d9c`
- `api-ms-win-core-threadpool-l1-2-0!FreeLibraryWhenCallbackReturns` at `0x180026dbc`
- `api-ms-win-core-threadpool-l1-2-0!FreeLibraryWhenCallbackReturns` at `0x180026dbc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026d03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026d5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026dd2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026d03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026d5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026dd2`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressSingle` at `0x180026daf`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressSingle` at `0x180026daf`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall DAS::Dispatcher::Dispatch::DispatchWorkCallback(PTP_CALLBACK_INSTANCE Instance, HMODULE *Context)
{
  PSRWLOCK v4; // rbx
  _DWORD *v5; // rcx
  char v6; // al
  int v7; // edx
  int v8; // r8d
  _QWORD *v9; // rdi
  HMODULE *v10; // [rsp+40h] [rbp-28h] BYREF
  DWORD CurrentThreadId; // [rsp+78h] [rbp+10h] BYREF
  RTL_SRWLOCK *v12; // [rsp+80h] [rbp+18h] BYREF
  PSRWLOCK SRWLock; // [rsp+88h] [rbp+20h] BYREF

  v10 = Context;
  *((_DWORD *)*Context + 3) = GetCurrentThreadId();
  wil::AcquireSRWLockShared(&SRWLock, &DAS::Dispatcher::g_dispatcherLock);
  if ( DAS::Dispatcher::g_dispatcherStopping )
  {
    *(_DWORD *)*Context = -2147023641;
  }
  else
  {
    DAS::Dispatcher::Watchdog::AddTimestamp(g_watchdog);
    *(_DWORD *)*Context = std::_Func_class<long,>::operator()(Context + 2);
    v4 = g_watchdog;
    wil::AcquireSRWLockExclusive(&v12, g_watchdog);
    CurrentThreadId = GetCurrentThreadId();
    std::_Tree<std::_Tmap_traits<unsigned long,_SYSTEMTIME,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,_SYSTEMTIME>>,0>>::erase(
      &v4[1],
      &CurrentThreadId);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v12);
  }
  if ( SRWLock )
    ReleaseSRWLockShared(SRWLock);
  v5 = *Context + 5;
  *v5 = 1;
  WakeByAddressSingle(v5);
  FreeLibraryWhenCallbackReturns(Instance, Context[14]);
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v6 = GetCurrentThreadId();
    v9 = Context + 10;
    if ( v9[3] > 7u )
      v9 = (_QWORD *)*v9;
    WPP_RECORDER_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v7,
      v8,
      13,
      &WPP_58cdcff8f7813eb890224e87d5cdb596_Traceguids,
      (__int64)v9,
      v6);
  }
  std::unique_ptr<DAS::Dispatcher::DispatchedArgs>::~unique_ptr<DAS::Dispatcher::DispatchedArgs>((DAS::Dispatcher::DispatchedArgs **)&v10);
}

```

## disassembly

```asm
0x180026cf0  push    rbx
0x180026cf2  push    rsi
0x180026cf3  push    rdi
0x180026cf4  sub     rsp, 50h
0x180026cf8  mov     rdi, rdx
0x180026cfb  mov     rsi, rcx
0x180026cfe  mov     [rsp+68h+var_28], rdx
0x180026d03  call    cs:__imp_GetCurrentThreadId
0x180026d09  mov     r8, [rdi]
0x180026d0c  mov     [r8+0Ch], eax
0x180026d10  lea     rdx, ?g_dispatcherLock@Dispatcher@DAS@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK DAS::Dispatcher::g_dispatcherLock
0x180026d17  lea     rcx, [rsp+68h+SRWLock]
0x180026d1f  call    ?AcquireSRWLockShared@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockShared(_RTL_SRWLOCK *)
0x180026d24  nop
0x180026d25  cmp     cs:?g_dispatcherStopping@Dispatcher@DAS@@3_NA, 0; bool DAS::Dispatcher::g_dispatcherStopping
0x180026d2c  jnz     short loc_180026D86
0x180026d2e  mov     rcx, cs:?g_watchdog@@3V?$unique_ptr@VWatchdog@Dispatcher@DAS@@U?$default_delete@VWatchdog@Dispatcher@DAS@@@std@@@std@@A; SRWLock
0x180026d35  call    ?AddTimestamp@Watchdog@Dispatcher@DAS@@QEAAXXZ; DAS::Dispatcher::Watchdog::AddTimestamp(void)
0x180026d3a  lea     rcx, [rdi+10h]
0x180026d3e  call    ??R?$_Func_class@J$$V@std@@QEBAJXZ; std::_Func_class<long,>::operator()(void)
0x180026d43  mov     rcx, [rdi]
0x180026d46  mov     [rcx], eax
0x180026d48  mov     rbx, cs:?g_watchdog@@3V?$unique_ptr@VWatchdog@Dispatcher@DAS@@U?$default_delete@VWatchdog@Dispatcher@DAS@@@std@@@std@@A; std::unique_ptr<DAS::Dispatcher::Watchdog> g_watchdog
0x180026d4f  mov     rdx, rbx
0x180026d52  lea     rcx, [rsp+68h+arg_10]
0x180026d5a  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x180026d5f  call    cs:__imp_GetCurrentThreadId
0x180026d65  mov     [rsp+68h+arg_8], eax
0x180026d69  lea     rcx, [rbx+8]
0x180026d6d  lea     rdx, [rsp+68h+arg_8]
0x180026d72  call    ?erase@?$_Tree@V?$_Tmap_traits@KU_SYSTEMTIME@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKU_SYSTEMTIME@@@std@@@3@$0A@@std@@@std@@QEAA_KAEBK@Z; std::_Tree<std::_Tmap_traits<ulong,_SYSTEMTIME,std::less<ulong>,std::allocator<std::pair<ulong const,_SYSTEMTIME>>,0>>::erase(ulong const &)
0x180026d77  lea     rcx, [rsp+68h+arg_10]
0x180026d7f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180026d84  jmp     short loc_180026D8F
0x180026d86  mov     rax, [rdi]
0x180026d89  mov     dword ptr [rax], 800704E7h
0x180026d8f  mov     rcx, [rsp+68h+SRWLock]; SRWLock
0x180026d97  test    rcx, rcx
0x180026d9a  jz      short loc_180026DA2
0x180026d9c  call    cs:__imp_ReleaseSRWLockShared
0x180026da2  mov     rcx, [rdi]
0x180026da5  add     rcx, 14h; Address
0x180026da9  mov     dword ptr [rcx], 1
0x180026daf  call    cs:__imp_WakeByAddressSingle
0x180026db5  mov     rdx, [rdi+70h]; mod
0x180026db9  mov     rcx, rsi; pci
0x180026dbc  call    cs:__imp_FreeLibraryWhenCallbackReturns
0x180026dc2  lea     rax, WPP_RECORDER_INITIALIZED
0x180026dc9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180026dd0  jz      short loc_180026E12
0x180026dd2  call    cs:__imp_GetCurrentThreadId
0x180026dd8  add     rdi, 50h ; 'P'
0x180026ddc  cmp     qword ptr [rdi+18h], 7
0x180026de1  jbe     short loc_180026DE6
0x180026de3  mov     rdi, [rdi]
0x180026de6  mov     r9d, 0Dh; int
0x180026dec  mov     dword ptr [rsp+68h+var_38], eax; char
0x180026df0  mov     [rsp+68h+var_40], rdi; __int64
0x180026df5  lea     rax, WPP_58cdcff8f7813eb890224e87d5cdb596_Traceguids
0x180026dfc  mov     [rsp+68h+MessageGuid], rax; MessageGuid
0x180026e01  mov     rcx, cs:WPP_GLOBAL_Control
0x180026e08  mov     rcx, [rcx+28h]; int
0x180026e0c  call    WPP_RECORDER_SF_Sd
0x180026e11  nop
0x180026e12  lea     rcx, [rsp+68h+var_28]
0x180026e17  call    ??1?$unique_ptr@UDispatchedArgs@Dispatcher@DAS@@U?$default_delete@UDispatchedArgs@Dispatcher@DAS@@@std@@@std@@QEAA@XZ; std::unique_ptr<DAS::Dispatcher::DispatchedArgs>::~unique_ptr<DAS::Dispatcher::DispatchedArgs>(void)
0x180026e1c  add     rsp, 50h
0x180026e20  pop     rdi
0x180026e21  pop     rsi
0x180026e22  pop     rbx
0x180026e23  retn
```
