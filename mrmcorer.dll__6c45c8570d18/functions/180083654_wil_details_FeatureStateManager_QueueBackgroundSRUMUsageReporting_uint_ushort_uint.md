# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180083654`
- end: `0x180083737`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `227`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800801a0`

## callees

- `0x18005cb34`
- `0x18005d6b4`
- `0x18005dafc`
- `0x18005db40`
- `0x180071784`
- `0x180075e08`
- `0x180075ec8`
- `0x180083654`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180083690`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180083690`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800836ec`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800836ec`

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
  int Src; // [rsp+28h] [rbp-30h] BYREF
  __int16 v11; // [rsp+2Ch] [rbp-2Ch]
  __int16 v12; // [rsp+2Eh] [rbp-2Ah]
  int v13; // [rsp+30h] [rbp-28h]
  char v14; // [rsp+60h] [rbp+8h] BYREF

  if ( *pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v9 = pv + 40;
    v12 = 0;
    Src = a2;
    v11 = a3;
    v13 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 232), &Src, 0xCu);
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
0x180083654  mov     [rsp+arg_8], rbx
0x180083659  mov     [rsp+arg_10], rbp
0x18008365e  push    rsi
0x18008365f  push    rdi
0x180083660  push    r14
0x180083662  sub     rsp, 40h
0x180083666  mov     esi, r9d
0x180083669  movzx   ebp, r8w
0x18008366d  mov     r14d, edx
0x180083670  mov     rdi, rcx
0x180083673  cmp     byte ptr [rcx], 0
0x180083676  jz      loc_180083724
0x18008367c  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180083681  test    al, al
0x180083683  jnz     loc_180083724
0x180083689  lea     rbx, [rdi+28h]
0x18008368d  mov     rcx, rbx; SRWLock
0x180083690  call    cs:__imp_AcquireSRWLockExclusive
0x180083696  mov     [rsp+58h+var_38], rbx
0x18008369b  xor     eax, eax
0x18008369d  mov     [rsp+58h+var_2A], ax
0x1800836a2  mov     [rsp+58h+Src], r14d
0x1800836a7  mov     [rsp+58h+var_2C], bp
0x1800836ac  mov     [rsp+58h+var_28], esi
0x1800836b0  lea     rcx, [rdi+0E8h]; this
0x1800836b7  lea     r8d, [rax+0Ch]; Size
0x1800836bb  lea     rdx, [rsp+58h+Src]; Src
0x1800836c0  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800836c5  cmp     byte ptr [rdi+40h], 0
0x1800836c9  jnz     short loc_180083719
0x1800836cb  lea     rbx, [rdi+38h]
0x1800836cf  cmp     qword ptr [rbx], 0
0x1800836d3  jnz     short loc_180083707
0x1800836d5  lea     rcx, [rsp+58h+arg_0]; this
0x1800836da  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800836df  xor     r8d, r8d; pcbe
0x1800836e2  mov     rdx, rdi; pv
0x1800836e5  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800836ec  call    cs:__imp_CreateThreadpoolTimer
0x1800836f2  mov     rdx, rax
0x1800836f5  mov     rcx, rbx
0x1800836f8  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800836fd  lea     rcx, [rsp+58h+arg_0]; this
0x180083702  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180083707  mov     r8d, 1388h
0x18008370d  lea     rdx, [rdi+40h]
0x180083711  mov     rcx, rbx
0x180083714  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180083719  lea     rcx, [rsp+58h+var_38]
0x18008371e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180083723  nop
0x180083724  mov     rbx, [rsp+58h+arg_8]
0x180083729  mov     rbp, [rsp+58h+arg_10]
0x18008372e  add     rsp, 40h
0x180083732  pop     r14
0x180083734  pop     rdi
0x180083735  pop     rsi
0x180083736  retn
```
