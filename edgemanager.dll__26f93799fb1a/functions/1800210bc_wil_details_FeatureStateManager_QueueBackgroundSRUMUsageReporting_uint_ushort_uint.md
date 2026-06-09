# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1800210bc`
- end: `0x18002119f`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `227`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800760d0`

## callees

- `0x1800210bc`
- `0x180021270`
- `0x180021290`
- `0x1800212d4`
- `0x1800212f4`
- `0x180021318`
- `0x180023a30`
- `0x180076314`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800210f8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800210f8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180021154`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180021154`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        char *pv,
        int a2,
        __int16 a3,
        int a4)
{
  PTP_TIMER ThreadpoolTimer; // rax
  char *v9; // [rsp+20h] [rbp-38h] BYREF
  int v10; // [rsp+28h] [rbp-30h] BYREF
  __int16 v11; // [rsp+2Ch] [rbp-2Ch]
  __int16 v12; // [rsp+2Eh] [rbp-2Ah]
  int v13; // [rsp+30h] [rbp-28h]
  char v14; // [rsp+60h] [rbp+8h] BYREF

  if ( *pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v9 = pv + 40;
    v12 = 0;
    v10 = a2;
    v11 = a3;
    v13 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 232), &v10, 0xCu);
    if ( !pv[64] )
    {
      if ( !*((_QWORD *)pv + 7) )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v14);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          pv + 56,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v14);
      }
      wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)pv + 7, pv + 64, 5000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  }
}

```

## disassembly

```asm
0x1800210bc  mov     [rsp+arg_8], rbx
0x1800210c1  mov     [rsp+arg_10], rbp
0x1800210c6  push    rsi
0x1800210c7  push    rdi
0x1800210c8  push    r14
0x1800210ca  sub     rsp, 40h
0x1800210ce  mov     esi, r9d
0x1800210d1  movzx   ebp, r8w
0x1800210d5  mov     r14d, edx
0x1800210d8  mov     rdi, rcx
0x1800210db  cmp     byte ptr [rcx], 0
0x1800210de  jz      loc_18002118C
0x1800210e4  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800210e9  test    al, al
0x1800210eb  jnz     loc_18002118C
0x1800210f1  lea     rbx, [rdi+28h]
0x1800210f5  mov     rcx, rbx; SRWLock
0x1800210f8  call    cs:__imp_AcquireSRWLockExclusive
0x1800210fe  mov     [rsp+58h+var_38], rbx
0x180021103  xor     eax, eax
0x180021105  mov     [rsp+58h+var_2A], ax
0x18002110a  mov     [rsp+58h+var_30], r14d
0x18002110f  mov     [rsp+58h+var_2C], bp
0x180021114  mov     [rsp+58h+var_28], esi
0x180021118  lea     rcx, [rdi+0E8h]; this
0x18002111f  lea     r8d, [rax+0Ch]; unsigned __int64
0x180021123  lea     rdx, [rsp+58h+var_30]; void *
0x180021128  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18002112d  cmp     byte ptr [rdi+40h], 0
0x180021131  jnz     short loc_180021181
0x180021133  lea     rbx, [rdi+38h]
0x180021137  cmp     qword ptr [rbx], 0
0x18002113b  jnz     short loc_18002116F
0x18002113d  lea     rcx, [rsp+58h+arg_0]; this
0x180021142  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180021147  xor     r8d, r8d; pcbe
0x18002114a  mov     rdx, rdi; pv
0x18002114d  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180021154  call    cs:__imp_CreateThreadpoolTimer
0x18002115a  mov     rdx, rax
0x18002115d  mov     rcx, rbx
0x180021160  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180021165  lea     rcx, [rsp+58h+arg_0]; this
0x18002116a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002116f  mov     r8d, 1388h
0x180021175  lea     rdx, [rdi+40h]
0x180021179  mov     rcx, rbx
0x18002117c  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180021181  lea     rcx, [rsp+58h+var_38]
0x180021186  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002118b  nop
0x18002118c  mov     rbx, [rsp+58h+arg_8]
0x180021191  mov     rbp, [rsp+58h+arg_10]
0x180021196  add     rsp, 40h
0x18002119a  pop     r14
0x18002119c  pop     rdi
0x18002119d  pop     rsi
0x18002119e  retn
```
