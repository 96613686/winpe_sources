# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180009dd8`
- end: `0x180009ebb`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `227`
- prototype: `void __fastcall(char *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000be90`

## callees

- `0x1800074a0`
- `0x180007984`
- `0x180007c98`
- `0x1800083a0`
- `0x180009da4`
- `0x180009dd8`
- `0x18000ca44`
- `0x18000cbf8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009e14`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009e14`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180009e70`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180009e70`

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

  if ( *pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v9 = (RTL_SRWLOCK *)(pv + 40);
    v12 = 0;
    v10 = a2;
    v11 = a3;
    v13 = a4;
    wil::details_abi::heap_buffer::push_back((void **)pv + 29, &v10, 0xCu);
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
0x180009dd8  mov     [rsp+arg_8], rbx
0x180009ddd  mov     [rsp+arg_10], rbp
0x180009de2  push    rsi
0x180009de3  push    rdi
0x180009de4  push    r14
0x180009de6  sub     rsp, 40h
0x180009dea  mov     esi, r9d
0x180009ded  movzx   ebp, r8w
0x180009df1  mov     r14d, edx
0x180009df4  mov     rdi, rcx
0x180009df7  cmp     byte ptr [rcx], 0
0x180009dfa  jz      loc_180009EA8
0x180009e00  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180009e05  test    al, al
0x180009e07  jnz     loc_180009EA8
0x180009e0d  lea     rbx, [rdi+28h]
0x180009e11  mov     rcx, rbx; SRWLock
0x180009e14  call    cs:__imp_AcquireSRWLockExclusive
0x180009e1a  mov     [rsp+58h+var_38], rbx
0x180009e1f  xor     eax, eax
0x180009e21  mov     [rsp+58h+var_2A], ax
0x180009e26  mov     [rsp+58h+var_30], r14d
0x180009e2b  mov     [rsp+58h+var_2C], bp
0x180009e30  mov     [rsp+58h+var_28], esi
0x180009e34  lea     rcx, [rdi+0E8h]; this
0x180009e3b  lea     r8d, [rax+0Ch]; unsigned __int64
0x180009e3f  lea     rdx, [rsp+58h+var_30]; void *
0x180009e44  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180009e49  cmp     byte ptr [rdi+40h], 0
0x180009e4d  jnz     short loc_180009E9D
0x180009e4f  lea     rbx, [rdi+38h]
0x180009e53  cmp     qword ptr [rbx], 0
0x180009e57  jnz     short loc_180009E8B
0x180009e59  lea     rcx, [rsp+58h+arg_0]; this
0x180009e5e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180009e63  xor     r8d, r8d; pcbe
0x180009e66  mov     rdx, rdi; pv
0x180009e69  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180009e70  call    cs:__imp_CreateThreadpoolTimer
0x180009e76  mov     rdx, rax
0x180009e79  mov     rcx, rbx
0x180009e7c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180009e81  lea     rcx, [rsp+58h+arg_0]; this
0x180009e86  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180009e8b  mov     r8d, 1388h
0x180009e91  lea     rdx, [rdi+40h]
0x180009e95  mov     rcx, rbx
0x180009e98  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180009e9d  lea     rcx, [rsp+58h+var_38]
0x180009ea2  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180009ea7  nop
0x180009ea8  mov     rbx, [rsp+58h+arg_8]
0x180009ead  mov     rbp, [rsp+58h+arg_10]
0x180009eb2  add     rsp, 40h
0x180009eb6  pop     r14
0x180009eb8  pop     rdi
0x180009eb9  pop     rsi
0x180009eba  retn
```
