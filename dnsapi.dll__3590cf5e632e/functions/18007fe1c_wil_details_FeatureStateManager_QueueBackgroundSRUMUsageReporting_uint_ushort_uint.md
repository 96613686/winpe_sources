# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18007fe1c`
- end: `0x18007ff17`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `251`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800c98f0`

## callees

- `0x18007fe1c`
- `0x1800800a4`
- `0x1800800c8`
- `0x18008012c`
- `0x180080150`
- `0x18008017c`
- `0x18008041c`
- `0x180080c38`
- `0x18008b5f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007fe5f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007fe5f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18007fec1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18007fec1`

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
0x18007fe1c  push    rbx
0x18007fe1e  push    rbp
0x18007fe1f  push    rsi
0x18007fe20  push    rdi
0x18007fe21  push    r14
0x18007fe23  sub     rsp, 50h
0x18007fe27  mov     rax, cs:__security_cookie
0x18007fe2e  xor     rax, rsp
0x18007fe31  mov     [rsp+78h+var_38], rax
0x18007fe36  cmp     byte ptr [rcx], 0
0x18007fe39  mov     r14d, r9d
0x18007fe3c  movzx   ebp, r8w
0x18007fe40  mov     esi, edx
0x18007fe42  mov     rdi, rcx
0x18007fe45  jz      loc_18007FEFE
0x18007fe4b  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18007fe50  test    al, al
0x18007fe52  jnz     loc_18007FEFE
0x18007fe58  lea     rbx, [rdi+28h]
0x18007fe5c  mov     rcx, rbx; SRWLock
0x18007fe5f  call    cs:__imp_AcquireSRWLockExclusive
0x18007fe66  nop     dword ptr [rax+rax+00h]
0x18007fe6b  xor     eax, eax
0x18007fe6d  mov     [rsp+78h+var_50], rbx
0x18007fe72  lea     rcx, [rdi+0E8h]; this
0x18007fe79  mov     [rsp+78h+var_42], ax
0x18007fe7e  lea     rdx, [rsp+78h+var_48]; void *
0x18007fe83  mov     [rsp+78h+var_48], esi
0x18007fe87  mov     [rsp+78h+var_44], bp
0x18007fe8c  lea     r8d, [rax+0Ch]; unsigned __int64
0x18007fe90  mov     [rsp+78h+var_40], r14d
0x18007fe95  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18007fe9a  cmp     byte ptr [rdi+40h], 0
0x18007fe9e  jnz     short loc_18007FEF4
0x18007fea0  lea     rbx, [rdi+38h]
0x18007fea4  cmp     qword ptr [rbx], 0
0x18007fea8  jnz     short loc_18007FEE2
0x18007feaa  lea     rcx, [rsp+78h+var_58]; this
0x18007feaf  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18007feb4  xor     r8d, r8d; pcbe
0x18007feb7  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18007febe  mov     rdx, rdi; pv
0x18007fec1  call    cs:__imp_CreateThreadpoolTimer
0x18007fec8  nop     dword ptr [rax+rax+00h]
0x18007fecd  mov     rdx, rax
0x18007fed0  mov     rcx, rbx
0x18007fed3  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18007fed8  lea     rcx, [rsp+78h+var_58]; this
0x18007fedd  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18007fee2  mov     r8d, 1388h
0x18007fee8  lea     rdx, [rdi+40h]
0x18007feec  mov     rcx, rbx
0x18007feef  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18007fef4  lea     rcx, [rsp+78h+var_50]
0x18007fef9  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18007fefe  mov     rcx, [rsp+78h+var_38]
0x18007ff03  xor     rcx, rsp; StackCookie
0x18007ff06  call    __security_check_cookie
0x18007ff0b  add     rsp, 50h
0x18007ff0f  pop     r14
0x18007ff11  pop     rdi
0x18007ff12  pop     rsi
0x18007ff13  pop     rbp
0x18007ff14  pop     rbx
0x18007ff15  retn
```
