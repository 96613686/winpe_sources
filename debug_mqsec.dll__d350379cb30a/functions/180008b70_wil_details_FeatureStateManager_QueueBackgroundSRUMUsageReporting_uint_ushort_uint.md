# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180008b70`
- end: `0x180008c61`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `241`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000a8b0`

## callees

- `0x1800059c4`
- `0x180005c6c`
- `0x180005fd4`
- `0x1800065e0`
- `0x180008b3c`
- `0x180008b70`
- `0x18000ae64`
- `0x18000af74`
- `0x18002f0e0`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x180008bb3`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180008bb3`
- `KERNEL32!CreateThreadpoolTimer` at `0x180008c10`
- `KERNEL32!CreateThreadpoolTimer` at `0x180008c10`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180008b70  push    rbx
0x180008b72  push    rbp
0x180008b73  push    rsi
0x180008b74  push    rdi
0x180008b75  push    r14
0x180008b77  sub     rsp, 50h
0x180008b7b  mov     rax, cs:__security_cookie
0x180008b82  xor     rax, rsp
0x180008b85  mov     [rsp+78h+var_38], rax
0x180008b8a  mov     r14d, r9d
0x180008b8d  movzx   ebp, r8w
0x180008b91  mov     esi, edx
0x180008b93  mov     rdi, rcx
0x180008b96  cmp     byte ptr [rcx], 0
0x180008b99  jz      loc_180008C49
0x180008b9f  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180008ba4  test    al, al
0x180008ba6  jnz     loc_180008C49
0x180008bac  lea     rbx, [rdi+28h]
0x180008bb0  mov     rcx, rbx; SRWLock
0x180008bb3  call    cs:__imp_AcquireSRWLockExclusive
0x180008bb9  mov     [rsp+78h+var_50], rbx
0x180008bbe  xor     eax, eax
0x180008bc0  mov     [rsp+78h+var_42], ax
0x180008bc5  mov     [rsp+78h+var_48], esi
0x180008bc9  mov     [rsp+78h+var_44], bp
0x180008bce  mov     [rsp+78h+var_40], r14d
0x180008bd3  lea     rcx, [rdi+0E8h]; this
0x180008bda  lea     r8d, [rax+0Ch]; unsigned __int64
0x180008bde  lea     rdx, [rsp+78h+var_48]; void *
0x180008be3  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180008be8  nop
0x180008be9  cmp     byte ptr [rdi+40h], 0
0x180008bed  jnz     short loc_180008C3E
0x180008bef  lea     rbx, [rdi+38h]
0x180008bf3  cmp     qword ptr [rbx], 0
0x180008bf7  jnz     short loc_180008C2B
0x180008bf9  lea     rcx, [rsp+78h+var_58]; this
0x180008bfe  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180008c03  xor     r8d, r8d; pcbe
0x180008c06  mov     rdx, rdi; pv
0x180008c09  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180008c10  call    cs:__imp_CreateThreadpoolTimer
0x180008c16  mov     rdx, rax
0x180008c19  mov     rcx, rbx
0x180008c1c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180008c21  lea     rcx, [rsp+78h+var_58]; this
0x180008c26  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180008c2b  mov     r8d, 1388h
0x180008c31  lea     rdx, [rdi+40h]
0x180008c35  mov     rcx, rbx
0x180008c38  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180008c3d  nop
0x180008c3e  lea     rcx, [rsp+78h+var_50]
0x180008c43  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180008c48  nop
0x180008c49  mov     rcx, [rsp+78h+var_38]
0x180008c4e  xor     rcx, rsp; StackCookie
0x180008c51  call    __security_check_cookie
0x180008c56  add     rsp, 50h
0x180008c5a  pop     r14
0x180008c5c  pop     rdi
0x180008c5d  pop     rsi
0x180008c5e  pop     rbp
0x180008c5f  pop     rbx
0x180008c60  retn
```
