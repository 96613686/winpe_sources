# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180005ed0`
- end: `0x180005fbf`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `239`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800080a0`

## callees

- `0x180002fd4`
- `0x180003338`
- `0x1800036e0`
- `0x180003dc4`
- `0x180005e9c`
- `0x180005ed0`
- `0x180008d20`
- `0x180008e2c`
- `0x18002e230`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x180005f13`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180005f13`
- `KERNEL32!CreateThreadpoolTimer` at `0x180005f6f`
- `KERNEL32!CreateThreadpoolTimer` at `0x180005f6f`

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
0x180005ed0  push    rbx
0x180005ed2  push    rbp
0x180005ed3  push    rsi
0x180005ed4  push    rdi
0x180005ed5  push    r14
0x180005ed7  sub     rsp, 50h
0x180005edb  mov     rax, cs:__security_cookie
0x180005ee2  xor     rax, rsp
0x180005ee5  mov     [rsp+78h+var_38], rax
0x180005eea  mov     r14d, r9d
0x180005eed  movzx   ebp, r8w
0x180005ef1  mov     esi, edx
0x180005ef3  mov     rdi, rcx
0x180005ef6  cmp     byte ptr [rcx], 0
0x180005ef9  jz      loc_180005FA7
0x180005eff  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180005f04  test    al, al
0x180005f06  jnz     loc_180005FA7
0x180005f0c  lea     rbx, [rdi+28h]
0x180005f10  mov     rcx, rbx; SRWLock
0x180005f13  call    cs:__imp_AcquireSRWLockExclusive
0x180005f19  mov     [rsp+78h+var_50], rbx
0x180005f1e  xor     eax, eax
0x180005f20  mov     [rsp+78h+var_42], ax
0x180005f25  mov     [rsp+78h+var_48], esi
0x180005f29  mov     [rsp+78h+var_44], bp
0x180005f2e  mov     [rsp+78h+var_40], r14d
0x180005f33  lea     rcx, [rdi+0E8h]; this
0x180005f3a  lea     r8d, [rax+0Ch]; unsigned __int64
0x180005f3e  lea     rdx, [rsp+78h+var_48]; void *
0x180005f43  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180005f48  cmp     byte ptr [rdi+40h], 0
0x180005f4c  jnz     short loc_180005F9C
0x180005f4e  lea     rbx, [rdi+38h]
0x180005f52  cmp     qword ptr [rbx], 0
0x180005f56  jnz     short loc_180005F8A
0x180005f58  lea     rcx, [rsp+78h+var_58]; this
0x180005f5d  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180005f62  xor     r8d, r8d; pcbe
0x180005f65  mov     rdx, rdi; pv
0x180005f68  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180005f6f  call    cs:__imp_CreateThreadpoolTimer
0x180005f75  mov     rdx, rax
0x180005f78  mov     rcx, rbx
0x180005f7b  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180005f80  lea     rcx, [rsp+78h+var_58]; this
0x180005f85  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180005f8a  mov     r8d, 1388h
0x180005f90  lea     rdx, [rdi+40h]
0x180005f94  mov     rcx, rbx
0x180005f97  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180005f9c  lea     rcx, [rsp+78h+var_50]
0x180005fa1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180005fa6  nop
0x180005fa7  mov     rcx, [rsp+78h+var_38]
0x180005fac  xor     rcx, rsp; StackCookie
0x180005faf  call    __security_check_cookie
0x180005fb4  add     rsp, 50h
0x180005fb8  pop     r14
0x180005fba  pop     rdi
0x180005fbb  pop     rsi
0x180005fbc  pop     rbp
0x180005fbd  pop     rbx
0x180005fbe  retn
```
