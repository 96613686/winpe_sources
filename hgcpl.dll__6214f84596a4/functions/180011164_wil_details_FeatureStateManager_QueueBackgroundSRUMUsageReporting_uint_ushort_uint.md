# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180011164`
- end: `0x180011252`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `238`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800121a0`

## callees

- `0x180004728`
- `0x1800049c0`
- `0x180005f3c`
- `0x1800070ac`
- `0x180010538`
- `0x180011164`
- `0x180012570`
- `0x18001267c`
- `0x180018a80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800111a7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800111a7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180011203`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180011203`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        char *pv,
        int a2,
        __int16 a3,
        int a4)
{
  PTP_TIMER ThreadpoolTimer; // rax
  _BYTE v9[8]; // [rsp+20h] [rbp-58h] BYREF
  char *v10; // [rsp+28h] [rbp-50h] BYREF
  int v11; // [rsp+30h] [rbp-48h] BYREF
  __int16 v12; // [rsp+34h] [rbp-44h]
  __int16 v13; // [rsp+36h] [rbp-42h]
  int v14; // [rsp+38h] [rbp-40h]

  if ( *pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v10 = pv + 40;
    v13 = 0;
    v11 = a2;
    v12 = a3;
    v14 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 232), &v11, 0xCu);
    if ( !pv[64] )
    {
      if ( !*((_QWORD *)pv + 7) )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v9);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          pv + 56,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v9);
      }
      wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)pv + 7, pv + 64, 5000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  }
}

```

## disassembly

```asm
0x180011164  push    rbx
0x180011166  push    rbp
0x180011167  push    rsi
0x180011168  push    rdi
0x180011169  push    r14
0x18001116b  sub     rsp, 50h
0x18001116f  mov     rax, cs:__security_cookie
0x180011176  xor     rax, rsp
0x180011179  mov     [rsp+78h+var_38], rax
0x18001117e  cmp     byte ptr [rcx], 0
0x180011181  mov     r14d, r9d
0x180011184  movzx   ebp, r8w
0x180011188  mov     esi, edx
0x18001118a  mov     rdi, rcx
0x18001118d  jz      loc_18001123A
0x180011193  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180011198  test    al, al
0x18001119a  jnz     loc_18001123A
0x1800111a0  lea     rbx, [rdi+28h]
0x1800111a4  mov     rcx, rbx; SRWLock
0x1800111a7  call    cs:__imp_AcquireSRWLockExclusive
0x1800111ad  xor     eax, eax
0x1800111af  mov     [rsp+78h+var_50], rbx
0x1800111b4  lea     rcx, [rdi+0E8h]; this
0x1800111bb  mov     [rsp+78h+var_42], ax
0x1800111c0  lea     rdx, [rsp+78h+var_48]; void *
0x1800111c5  mov     [rsp+78h+var_48], esi
0x1800111c9  mov     [rsp+78h+var_44], bp
0x1800111ce  lea     r8d, [rax+0Ch]; unsigned __int64
0x1800111d2  mov     [rsp+78h+var_40], r14d
0x1800111d7  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800111dc  cmp     byte ptr [rdi+40h], 0
0x1800111e0  jnz     short loc_180011230
0x1800111e2  lea     rbx, [rdi+38h]
0x1800111e6  cmp     qword ptr [rbx], 0
0x1800111ea  jnz     short loc_18001121E
0x1800111ec  lea     rcx, [rsp+78h+var_58]; this
0x1800111f1  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800111f6  xor     r8d, r8d; pcbe
0x1800111f9  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180011200  mov     rdx, rdi; pv
0x180011203  call    cs:__imp_CreateThreadpoolTimer
0x180011209  mov     rdx, rax
0x18001120c  mov     rcx, rbx
0x18001120f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180011214  lea     rcx, [rsp+78h+var_58]; this
0x180011219  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001121e  mov     r8d, 1388h
0x180011224  lea     rdx, [rdi+40h]
0x180011228  mov     rcx, rbx
0x18001122b  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180011230  lea     rcx, [rsp+78h+var_50]
0x180011235  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001123a  mov     rcx, [rsp+78h+var_38]
0x18001123f  xor     rcx, rsp; StackCookie
0x180011242  call    __security_check_cookie
0x180011247  add     rsp, 50h
0x18001124b  pop     r14
0x18001124d  pop     rdi
0x18001124e  pop     rsi
0x18001124f  pop     rbp
0x180011250  pop     rbx
0x180011251  retn
```
