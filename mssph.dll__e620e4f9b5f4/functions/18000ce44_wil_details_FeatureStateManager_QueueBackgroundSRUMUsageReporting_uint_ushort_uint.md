# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000ce44`
- end: `0x18000cf2e`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `234`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800152f0`

## callees

- `0x18000b4e0`
- `0x18000c010`
- `0x18000ce44`
- `0x18000d008`
- `0x18000d118`
- `0x18000d138`
- `0x180015b28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ce80`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ce80`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cef8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cef8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000cedc`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000cedc`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        char *pv,
        int a2,
        __int16 a3,
        int a4)
{
  PTP_TIMER ThreadpoolTimer; // rax
  RTL_SRWLOCK *v9; // [rsp+20h] [rbp-38h] BYREF
  int v10; // [rsp+28h] [rbp-30h] BYREF
  __int16 v11; // [rsp+2Ch] [rbp-2Ch]
  __int16 v12; // [rsp+2Eh] [rbp-2Ah]
  int v13; // [rsp+30h] [rbp-28h]
  char v14; // [rsp+60h] [rbp+8h] BYREF
  DWORD dwErrCode; // [rsp+64h] [rbp+Ch]

  if ( *pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v9 = (RTL_SRWLOCK *)(pv + 40);
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
        if ( !v14 )
          SetLastError(dwErrCode);
      }
      wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)pv + 7, pv + 64, 5000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  }
}

```

## disassembly

```asm
0x18000ce44  mov     [rsp+arg_8], rbx
0x18000ce49  mov     [rsp+arg_10], rbp
0x18000ce4e  push    rsi
0x18000ce4f  push    rdi
0x18000ce50  push    r14
0x18000ce52  sub     rsp, 40h
0x18000ce56  mov     esi, r9d
0x18000ce59  movzx   ebp, r8w
0x18000ce5d  mov     r14d, edx
0x18000ce60  mov     rdi, rcx
0x18000ce63  cmp     byte ptr [rcx], 0
0x18000ce66  jz      loc_18000CF1B
0x18000ce6c  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18000ce71  test    al, al
0x18000ce73  jnz     loc_18000CF1B
0x18000ce79  lea     rbx, [rdi+28h]
0x18000ce7d  mov     rcx, rbx; SRWLock
0x18000ce80  call    cs:__imp_AcquireSRWLockExclusive
0x18000ce86  mov     [rsp+58h+var_38], rbx
0x18000ce8b  xor     eax, eax
0x18000ce8d  mov     [rsp+58h+var_2A], ax
0x18000ce92  mov     [rsp+58h+var_30], r14d
0x18000ce97  mov     [rsp+58h+var_2C], bp
0x18000ce9c  mov     [rsp+58h+var_28], esi
0x18000cea0  lea     rcx, [rdi+0E8h]; this
0x18000cea7  lea     r8d, [rax+0Ch]; unsigned __int64
0x18000ceab  lea     rdx, [rsp+58h+var_30]; void *
0x18000ceb0  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000ceb5  cmp     byte ptr [rdi+40h], 0
0x18000ceb9  jnz     short loc_18000CF10
0x18000cebb  lea     rbx, [rdi+38h]
0x18000cebf  cmp     qword ptr [rbx], 0
0x18000cec3  jnz     short loc_18000CEFE
0x18000cec5  lea     rcx, [rsp+58h+arg_0]; this
0x18000ceca  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000cecf  xor     r8d, r8d; pcbe
0x18000ced2  mov     rdx, rdi; pv
0x18000ced5  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000cedc  call    cs:__imp_CreateThreadpoolTimer
0x18000cee2  mov     rdx, rax
0x18000cee5  mov     rcx, rbx
0x18000cee8  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000ceed  cmp     [rsp+58h+arg_0], 0
0x18000cef2  jnz     short loc_18000CEFE
0x18000cef4  mov     ecx, [rsp+58h+dwErrCode]; dwErrCode
0x18000cef8  call    cs:__imp_SetLastError
0x18000cefe  mov     r8d, 1388h
0x18000cf04  lea     rdx, [rdi+40h]
0x18000cf08  mov     rcx, rbx
0x18000cf0b  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18000cf10  lea     rcx, [rsp+58h+var_38]
0x18000cf15  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000cf1a  nop
0x18000cf1b  mov     rbx, [rsp+58h+arg_8]
0x18000cf20  mov     rbp, [rsp+58h+arg_10]
0x18000cf25  add     rsp, 40h
0x18000cf29  pop     r14
0x18000cf2b  pop     rdi
0x18000cf2c  pop     rsi
0x18000cf2d  retn
```
