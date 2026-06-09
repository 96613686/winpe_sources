# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18007ae98`
- end: `0x18007af86`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `238`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18007bf20`

## callees

- `0x180077db8`
- `0x180077fe0`
- `0x1800782e8`
- `0x180078b14`
- `0x18007ad60`
- `0x18007ae98`
- `0x18007d3e4`
- `0x18007d500`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18007aecb`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18007aecb`
- `KERNEL32!CreateThreadpoolTimer` at `0x18007af38`
- `KERNEL32!CreateThreadpoolTimer` at `0x18007af38`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        __int64 a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v5; // rcx
  int Ptr; // eax
  PTP_TIMER ThreadpoolTimer; // rax
  _QWORD v8[3]; // [rsp+20h] [rbp-18h] BYREF
  char v9; // [rsp+40h] [rbp+8h] BYREF
  RTL_SRWLOCK *v10; // [rsp+58h] [rbp+20h] BYREF

  if ( LODWORD(pv->Ptr) && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive(pv + 1);
    Ptr = (int)pv->Ptr;
    v10 = pv + 1;
    if ( Ptr )
    {
      if ( !wil::ProcessShutdownInProgress(v5) )
      {
        v8[0] = 58090573;
        v8[1] = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[6], v8, 0x10u);
        if ( !LOBYTE(pv[3].Ptr) )
        {
          if ( !pv[2].Ptr )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&v9);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              &pv[2],
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v9);
          }
          wil::details::EnsureCoalescedTimer_SetTimer(&pv[2], &pv[3], 300000);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  }
}

```

## disassembly

```asm
0x18007ae98  mov     [rsp+arg_8], rbx
0x18007ae9d  mov     [rsp+arg_10], rsi
0x18007aea2  push    rdi
0x18007aea3  sub     rsp, 30h
0x18007aea7  mov     eax, [rcx]
0x18007aea9  mov     rsi, r8
0x18007aeac  mov     rdi, rcx
0x18007aeaf  test    eax, eax
0x18007aeb1  jz      loc_18007AF75
0x18007aeb7  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18007aebc  test    al, al
0x18007aebe  jnz     loc_18007AF75
0x18007aec4  lea     rbx, [rdi+8]
0x18007aec8  mov     rcx, rbx; SRWLock
0x18007aecb  call    cs:__imp_AcquireSRWLockExclusive
0x18007aed2  nop     dword ptr [rax+rax+00h]
0x18007aed7  mov     eax, [rdi]
0x18007aed9  mov     [rsp+38h+arg_18], rbx
0x18007aede  test    eax, eax
0x18007aee0  jz      loc_18007AF6B
0x18007aee6  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18007aeeb  test    al, al
0x18007aeed  jnz     short loc_18007AF6B
0x18007aeef  lea     rcx, [rdi+30h]; this
0x18007aef3  mov     [rsp+38h+var_18], 376644Dh
0x18007aefc  mov     r8d, 10h; unsigned __int64
0x18007af02  mov     [rsp+38h+var_10], rsi
0x18007af07  lea     rdx, [rsp+38h+var_18]; void *
0x18007af0c  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18007af11  cmp     byte ptr [rdi+18h], 0
0x18007af15  jnz     short loc_18007AF6B
0x18007af17  lea     rbx, [rdi+10h]
0x18007af1b  cmp     qword ptr [rbx], 0
0x18007af1f  jnz     short loc_18007AF59
0x18007af21  lea     rcx, [rsp+38h+arg_0]; this
0x18007af26  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18007af2b  xor     r8d, r8d; pcbe
0x18007af2e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18007af35  mov     rdx, rdi; pv
0x18007af38  call    cs:__imp_CreateThreadpoolTimer
0x18007af3f  nop     dword ptr [rax+rax+00h]
0x18007af44  mov     rdx, rax
0x18007af47  mov     rcx, rbx
0x18007af4a  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18007af4f  lea     rcx, [rsp+38h+arg_0]; this
0x18007af54  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18007af59  mov     r8d, 493E0h
0x18007af5f  lea     rdx, [rdi+18h]
0x18007af63  mov     rcx, rbx
0x18007af66  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18007af6b  lea     rcx, [rsp+38h+arg_18]
0x18007af70  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18007af75  mov     rbx, [rsp+38h+arg_8]
0x18007af7a  mov     rsi, [rsp+38h+arg_10]
0x18007af7f  add     rsp, 30h
0x18007af83  pop     rdi
0x18007af84  retn
```
