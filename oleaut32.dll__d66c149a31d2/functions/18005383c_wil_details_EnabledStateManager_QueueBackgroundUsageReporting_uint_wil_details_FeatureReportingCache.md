# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18005383c`
- end: `0x180053914`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `216`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180054ad4`

## callees

- `0x18003567c`
- `0x18003577c`
- `0x18004cae0`
- `0x18004fd48`
- `0x180050148`
- `0x1800509f0`
- `0x18005383c`
- `0x180056888`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005386e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005386e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800538d0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800538d0`

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
                                `wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
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
0x18005383c  mov     [rsp+arg_8], rbx
0x180053841  push    rbp
0x180053842  push    rsi
0x180053843  push    rdi
0x180053844  sub     rsp, 30h
0x180053848  mov     eax, [rcx]
0x18005384a  mov     rsi, r8
0x18005384d  mov     ebp, edx
0x18005384f  mov     rdi, rcx
0x180053852  test    eax, eax
0x180053854  jz      loc_180053907
0x18005385a  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18005385f  test    al, al
0x180053861  jnz     loc_180053907
0x180053867  lea     rbx, [rdi+8]
0x18005386b  mov     rcx, rbx; SRWLock
0x18005386e  call    cs:__imp_AcquireSRWLockExclusive
0x180053874  mov     eax, [rdi]
0x180053876  mov     [rsp+48h+arg_18], rbx
0x18005387b  test    eax, eax
0x18005387d  jz      short loc_1800538FD
0x18005387f  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180053884  test    al, al
0x180053886  jnz     short loc_1800538FD
0x180053888  xor     eax, eax
0x18005388a  mov     [rsp+48h+var_28], ebp
0x18005388e  lea     rcx, [rdi+20h]; this
0x180053892  mov     [rsp+48h+var_24], eax
0x180053896  lea     rdx, [rsp+48h+var_28]; void *
0x18005389b  mov     [rsp+48h+var_20], rsi
0x1800538a0  lea     r8d, [rax+10h]; unsigned __int64
0x1800538a4  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800538a9  cmp     byte ptr [rdi+18h], 0
0x1800538ad  jnz     short loc_1800538FD
0x1800538af  lea     rbx, [rdi+10h]
0x1800538b3  cmp     qword ptr [rbx], 0
0x1800538b7  jnz     short loc_1800538EB
0x1800538b9  lea     rcx, [rsp+48h+arg_0]; this
0x1800538be  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800538c3  xor     r8d, r8d; pcbe
0x1800538c6  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVEnabledStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800538cd  mov     rdx, rdi; pv
0x1800538d0  call    cs:__imp_CreateThreadpoolTimer
0x1800538d6  mov     rdx, rax
0x1800538d9  mov     rcx, rbx
0x1800538dc  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800538e1  lea     rcx, [rsp+48h+arg_0]; this
0x1800538e6  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800538eb  mov     r8d, 493E0h
0x1800538f1  lea     rdx, [rdi+18h]
0x1800538f5  mov     rcx, rbx
0x1800538f8  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1800538fd  lea     rcx, [rsp+48h+arg_18]
0x180053902  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180053907  mov     rbx, [rsp+48h+arg_8]
0x18005390c  add     rsp, 30h
0x180053910  pop     rdi
0x180053911  pop     rsi
0x180053912  pop     rbp
0x180053913  retn
```
