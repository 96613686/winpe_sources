# `wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)'::`8'::_lambda_1_::_lambda_invoker_cdecl_(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x180004e30`
- end: `0x180004e75`
- name: `?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, RTL_SRWLOCK *Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18000336c`
- `0x180004e30`
- `0x180006ad8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004e49`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004e49`

## pseudocode

```c
void __fastcall `wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_(
        PTP_CALLBACK_INSTANCE Instance,
        RTL_SRWLOCK *Context,
        PTP_TIMER Timer)
{
  RTL_SRWLOCK *v4; // rbx
  RTL_SRWLOCK *v5; // [rsp+20h] [rbp-18h] BYREF

  if ( LOBYTE(Context->Ptr) )
  {
    v4 = Context + 4;
    AcquireSRWLockExclusive(Context + 4);
    v5 = v4;
    BYTE1(Context[8].Ptr) = 0;
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v5);
    wil::details::FeatureStateManager::FlushUsage((wil::details::FeatureStateManager *)Context);
  }
}

```

## disassembly

```asm
0x180004e30  mov     [rsp+arg_0], rbx
0x180004e35  push    rdi
0x180004e36  sub     rsp, 30h
0x180004e3a  cmp     byte ptr [rdx], 0
0x180004e3d  mov     rdi, rdx
0x180004e40  jz      short loc_180004E6A
0x180004e42  lea     rbx, [rdx+20h]
0x180004e46  mov     rcx, rbx; SRWLock
0x180004e49  call    cs:__imp_AcquireSRWLockExclusive
0x180004e4f  lea     rcx, [rsp+38h+var_18]
0x180004e54  mov     [rsp+38h+var_18], rbx
0x180004e59  mov     byte ptr [rdi+41h], 0
0x180004e5d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180004e62  mov     rcx, rdi; this
0x180004e65  call    ?FlushUsage@FeatureStateManager@details@wil@@QEAAXXZ; wil::details::FeatureStateManager::FlushUsage(void)
0x180004e6a  mov     rbx, [rsp+38h+arg_0]
0x180004e6f  add     rsp, 30h
0x180004e73  pop     rdi
0x180004e74  retn
```
