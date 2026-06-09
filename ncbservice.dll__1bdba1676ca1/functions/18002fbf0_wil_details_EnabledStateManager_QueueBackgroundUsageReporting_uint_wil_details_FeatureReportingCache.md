# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18002fbf0`
- end: `0x18002fcc8`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `216`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180030638`

## callees

- `0x18001a1f8`
- `0x18001a218`
- `0x18001a25c`
- `0x18001a27c`
- `0x18001a2a0`
- `0x18001a3c8`
- `0x18002fbf0`
- `0x180031814`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002fc22`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002fc22`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002fc84`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002fc84`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  int Ptr; // eax
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD v9[2]; // [rsp+20h] [rbp-28h] BYREF
  struct wil_details_FeatureReportingCache *v10; // [rsp+28h] [rbp-20h]
  char v11; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v12; // [rsp+68h] [rbp+20h] BYREF

  if ( LODWORD(pv->Ptr) && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive(pv + 1);
    Ptr = (int)pv->Ptr;
    v12 = pv + 1;
    if ( Ptr )
    {
      if ( !wil::ProcessShutdownInProgress(v6) )
      {
        v9[0] = a2;
        v9[1] = 0;
        v10 = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[4], v9, 0x10u);
        if ( !LOBYTE(pv[3].Ptr) )
        {
          if ( !pv[2].Ptr )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&v11);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              &pv[2],
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v11);
          }
          wil::details::EnsureCoalescedTimer_SetTimer(&pv[2], &pv[3], 300000);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v12);
  }
}

```

## disassembly

```asm
0x18002fbf0  mov     [rsp+arg_8], rbx
0x18002fbf5  push    rbp
0x18002fbf6  push    rsi
0x18002fbf7  push    rdi
0x18002fbf8  sub     rsp, 30h
0x18002fbfc  mov     eax, [rcx]
0x18002fbfe  mov     rsi, r8
0x18002fc01  mov     ebp, edx
0x18002fc03  mov     rdi, rcx
0x18002fc06  test    eax, eax
0x18002fc08  jz      loc_18002FCBB
0x18002fc0e  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18002fc13  test    al, al
0x18002fc15  jnz     loc_18002FCBB
0x18002fc1b  lea     rbx, [rdi+8]
0x18002fc1f  mov     rcx, rbx; SRWLock
0x18002fc22  call    cs:__imp_AcquireSRWLockExclusive
0x18002fc28  mov     eax, [rdi]
0x18002fc2a  mov     [rsp+48h+arg_18], rbx
0x18002fc2f  test    eax, eax
0x18002fc31  jz      short loc_18002FCB1
0x18002fc33  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18002fc38  test    al, al
0x18002fc3a  jnz     short loc_18002FCB1
0x18002fc3c  xor     eax, eax
0x18002fc3e  mov     [rsp+48h+var_28], ebp
0x18002fc42  lea     rcx, [rdi+20h]; this
0x18002fc46  mov     [rsp+48h+var_24], eax
0x18002fc4a  lea     rdx, [rsp+48h+var_28]; void *
0x18002fc4f  mov     [rsp+48h+var_20], rsi
0x18002fc54  lea     r8d, [rax+10h]; unsigned __int64
0x18002fc58  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18002fc5d  cmp     byte ptr [rdi+18h], 0
0x18002fc61  jnz     short loc_18002FCB1
0x18002fc63  lea     rbx, [rdi+10h]
0x18002fc67  cmp     qword ptr [rbx], 0
0x18002fc6b  jnz     short loc_18002FC9F
0x18002fc6d  lea     rcx, [rsp+48h+arg_0]; this
0x18002fc72  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002fc77  xor     r8d, r8d; pcbe
0x18002fc7a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18002fc81  mov     rdx, rdi; pv
0x18002fc84  call    cs:__imp_CreateThreadpoolTimer
0x18002fc8a  mov     rdx, rax
0x18002fc8d  mov     rcx, rbx
0x18002fc90  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18002fc95  lea     rcx, [rsp+48h+arg_0]; this
0x18002fc9a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002fc9f  mov     r8d, 493E0h
0x18002fca5  lea     rdx, [rdi+18h]
0x18002fca9  mov     rcx, rbx
0x18002fcac  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18002fcb1  lea     rcx, [rsp+48h+arg_18]
0x18002fcb6  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002fcbb  mov     rbx, [rsp+48h+arg_8]
0x18002fcc0  add     rsp, 30h
0x18002fcc4  pop     rdi
0x18002fcc5  pop     rsi
0x18002fcc6  pop     rbp
0x18002fcc7  retn
```
