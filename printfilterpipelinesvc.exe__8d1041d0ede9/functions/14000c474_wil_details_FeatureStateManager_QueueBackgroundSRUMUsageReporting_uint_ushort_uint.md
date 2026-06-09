# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x14000c474`
- end: `0x14000c557`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `227`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14000e590`

## callees

- `0x140009174`
- `0x1400094d4`
- `0x140009828`
- `0x140009f64`
- `0x14000c440`
- `0x14000c474`
- `0x14000ec48`
- `0x14000ed50`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x14000c50c`
- `KERNEL32!CreateThreadpoolTimer` at `0x14000c50c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000c4b0`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000c4b0`

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
0x14000c474  mov     [rsp+arg_8], rbx
0x14000c479  mov     [rsp+arg_10], rbp
0x14000c47e  push    rsi
0x14000c47f  push    rdi
0x14000c480  push    r14
0x14000c482  sub     rsp, 40h
0x14000c486  mov     esi, r9d
0x14000c489  movzx   ebp, r8w
0x14000c48d  mov     r14d, edx
0x14000c490  mov     rdi, rcx
0x14000c493  cmp     byte ptr [rcx], 0
0x14000c496  jz      loc_14000C544
0x14000c49c  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x14000c4a1  test    al, al
0x14000c4a3  jnz     loc_14000C544
0x14000c4a9  lea     rbx, [rdi+28h]
0x14000c4ad  mov     rcx, rbx; SRWLock
0x14000c4b0  call    cs:__imp_AcquireSRWLockExclusive
0x14000c4b6  mov     [rsp+58h+var_38], rbx
0x14000c4bb  xor     eax, eax
0x14000c4bd  mov     [rsp+58h+var_2A], ax
0x14000c4c2  mov     [rsp+58h+var_30], r14d
0x14000c4c7  mov     [rsp+58h+var_2C], bp
0x14000c4cc  mov     [rsp+58h+var_28], esi
0x14000c4d0  lea     rcx, [rdi+0E8h]; this
0x14000c4d7  lea     r8d, [rax+0Ch]; unsigned __int64
0x14000c4db  lea     rdx, [rsp+58h+var_30]; void *
0x14000c4e0  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x14000c4e5  cmp     byte ptr [rdi+40h], 0
0x14000c4e9  jnz     short loc_14000C539
0x14000c4eb  lea     rbx, [rdi+38h]
0x14000c4ef  cmp     qword ptr [rbx], 0
0x14000c4f3  jnz     short loc_14000C527
0x14000c4f5  lea     rcx, [rsp+58h+arg_0]; this
0x14000c4fa  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14000c4ff  xor     r8d, r8d; pcbe
0x14000c502  mov     rdx, rdi; pv
0x14000c505  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14000c50c  call    cs:__imp_CreateThreadpoolTimer
0x14000c512  mov     rdx, rax
0x14000c515  mov     rcx, rbx
0x14000c518  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x14000c51d  lea     rcx, [rsp+58h+arg_0]; this
0x14000c522  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14000c527  mov     r8d, 1388h
0x14000c52d  lea     rdx, [rdi+40h]
0x14000c531  mov     rcx, rbx
0x14000c534  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x14000c539  lea     rcx, [rsp+58h+var_38]
0x14000c53e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000c543  nop
0x14000c544  mov     rbx, [rsp+58h+arg_8]
0x14000c549  mov     rbp, [rsp+58h+arg_10]
0x14000c54e  add     rsp, 40h
0x14000c552  pop     r14
0x14000c554  pop     rdi
0x14000c555  pop     rsi
0x14000c556  retn
```
