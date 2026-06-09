# `wil::details::EnsureCoalescedTimerSRUM<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)'::`8'::_lambda_1_::_lambda_invoker_cdecl_(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x140006aa0`
- end: `0x140006b03`
- name: `?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimerSRUM@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `99`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x140004dcc`
- `0x140006aa0`
- `0x14000bcec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140006ab9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140006ab9`

## pseudocode

```c
void __fastcall `wil::details::EnsureCoalescedTimerSRUM<wil::details::FeatureStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_(
        PTP_CALLBACK_INSTANCE Instance,
        char *Context,
        PTP_TIMER Timer)
{
  char *v4; // rbx
  char *v5; // [rsp+38h] [rbp+10h] BYREF

  if ( *Context )
  {
    v4 = Context + 40;
    AcquireSRWLockExclusive((PSRWLOCK)Context + 5);
    v5 = v4;
    if ( *((_QWORD *)Context + 30) - *((_QWORD *)Context + 29) >= 0xCu )
    {
      wil_details_WriteSRUMWnfUsageBuffer((__int64 *)Context + 29);
      *((_QWORD *)Context + 30) = *((_QWORD *)Context + 29);
    }
    Context[64] = 0;
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v5);
  }
}

```

## disassembly

```asm
0x140006aa0  mov     [rsp+arg_0], rbx
0x140006aa5  push    rdi
0x140006aa6  sub     rsp, 20h
0x140006aaa  cmp     byte ptr [rdx], 0
0x140006aad  mov     rdi, rdx
0x140006ab0  jz      short loc_140006AF8
0x140006ab2  lea     rbx, [rdx+28h]
0x140006ab6  mov     rcx, rbx; SRWLock
0x140006ab9  call    cs:__imp_AcquireSRWLockExclusive
0x140006abf  mov     [rsp+28h+arg_8], rbx
0x140006ac4  lea     rbx, [rdi+0E8h]
0x140006acb  mov     rax, [rbx+8]
0x140006acf  sub     rax, [rbx]
0x140006ad2  cmp     rax, 0Ch
0x140006ad6  jb      short loc_140006AEA
0x140006ad8  mov     rcx, rbx
0x140006adb  call    ?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z; wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)
0x140006ae0  mov     rax, [rbx]
0x140006ae3  mov     [rdi+0F0h], rax
0x140006aea  lea     rcx, [rsp+28h+arg_8]
0x140006aef  mov     byte ptr [rdi+40h], 0
0x140006af3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140006af8  mov     rbx, [rsp+28h+arg_0]
0x140006afd  add     rsp, 20h
0x140006b01  pop     rdi
0x140006b02  retn
```
