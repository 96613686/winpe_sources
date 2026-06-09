# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18002b9ec`
- end: `0x18002badb`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `239`
- prototype: `void __fastcall(char *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18002de20`

## callees

- `0x1800277e4`
- `0x180027a6c`
- `0x180027dd8`
- `0x1800289e4`
- `0x18002b9b8`
- `0x18002b9ec`
- `0x18002e58c`
- `0x18002e69c`
- `0x180031680`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18002ba2f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002ba2f`
- `KERNEL32!CreateThreadpoolTimer` at `0x18002ba8b`
- `KERNEL32!CreateThreadpoolTimer` at `0x18002ba8b`

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
  RTL_SRWLOCK *v10; // [rsp+28h] [rbp-50h] BYREF
  int v11; // [rsp+30h] [rbp-48h] BYREF
  __int16 v12; // [rsp+34h] [rbp-44h]
  __int16 v13; // [rsp+36h] [rbp-42h]
  int v14; // [rsp+38h] [rbp-40h]

  if ( *pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v10 = (RTL_SRWLOCK *)(pv + 40);
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
0x18002b9ec  push    rbx
0x18002b9ee  push    rbp
0x18002b9ef  push    rsi
0x18002b9f0  push    rdi
0x18002b9f1  push    r14
0x18002b9f3  sub     rsp, 50h
0x18002b9f7  mov     rax, cs:__security_cookie
0x18002b9fe  xor     rax, rsp
0x18002ba01  mov     [rsp+78h+var_38], rax
0x18002ba06  mov     r14d, r9d
0x18002ba09  movzx   ebp, r8w
0x18002ba0d  mov     esi, edx
0x18002ba0f  mov     rdi, rcx
0x18002ba12  cmp     byte ptr [rcx], 0
0x18002ba15  jz      loc_18002BAC3
0x18002ba1b  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18002ba20  test    al, al
0x18002ba22  jnz     loc_18002BAC3
0x18002ba28  lea     rbx, [rdi+28h]
0x18002ba2c  mov     rcx, rbx; SRWLock
0x18002ba2f  call    cs:__imp_AcquireSRWLockExclusive
0x18002ba35  mov     [rsp+78h+var_50], rbx
0x18002ba3a  xor     eax, eax
0x18002ba3c  mov     [rsp+78h+var_42], ax
0x18002ba41  mov     [rsp+78h+var_48], esi
0x18002ba45  mov     [rsp+78h+var_44], bp
0x18002ba4a  mov     [rsp+78h+var_40], r14d
0x18002ba4f  lea     rcx, [rdi+0E8h]; this
0x18002ba56  lea     r8d, [rax+0Ch]; unsigned __int64
0x18002ba5a  lea     rdx, [rsp+78h+var_48]; void *
0x18002ba5f  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18002ba64  cmp     byte ptr [rdi+40h], 0
0x18002ba68  jnz     short loc_18002BAB8
0x18002ba6a  lea     rbx, [rdi+38h]
0x18002ba6e  cmp     qword ptr [rbx], 0
0x18002ba72  jnz     short loc_18002BAA6
0x18002ba74  lea     rcx, [rsp+78h+var_58]; this
0x18002ba79  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002ba7e  xor     r8d, r8d; pcbe
0x18002ba81  mov     rdx, rdi; pv
0x18002ba84  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18002ba8b  call    cs:__imp_CreateThreadpoolTimer
0x18002ba91  mov     rdx, rax
0x18002ba94  mov     rcx, rbx
0x18002ba97  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18002ba9c  lea     rcx, [rsp+78h+var_58]; this
0x18002baa1  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002baa6  mov     r8d, 1388h
0x18002baac  lea     rdx, [rdi+40h]
0x18002bab0  mov     rcx, rbx
0x18002bab3  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18002bab8  lea     rcx, [rsp+78h+var_50]
0x18002babd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002bac2  nop
0x18002bac3  mov     rcx, [rsp+78h+var_38]
0x18002bac8  xor     rcx, rsp; StackCookie
0x18002bacb  call    __security_check_cookie
0x18002bad0  add     rsp, 50h
0x18002bad4  pop     r14
0x18002bad6  pop     rdi
0x18002bad7  pop     rsi
0x18002bad8  pop     rbp
0x18002bad9  pop     rbx
0x18002bada  retn
```
