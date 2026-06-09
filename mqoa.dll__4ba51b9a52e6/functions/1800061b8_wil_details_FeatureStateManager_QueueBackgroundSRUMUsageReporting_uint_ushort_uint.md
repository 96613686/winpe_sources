# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1800061b8`
- end: `0x1800062a9`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `241`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180007df0`

## callees

- `0x1800033b8`
- `0x18000376c`
- `0x180003b1c`
- `0x18000425c`
- `0x180006184`
- `0x1800061b8`
- `0x1800088f8`
- `0x180008a9c`
- `0x1800273b0`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x1800061fb`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800061fb`
- `KERNEL32!CreateThreadpoolTimer` at `0x180006258`
- `KERNEL32!CreateThreadpoolTimer` at `0x180006258`

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
0x1800061b8  push    rbx
0x1800061ba  push    rbp
0x1800061bb  push    rsi
0x1800061bc  push    rdi
0x1800061bd  push    r14
0x1800061bf  sub     rsp, 50h
0x1800061c3  mov     rax, cs:__security_cookie
0x1800061ca  xor     rax, rsp
0x1800061cd  mov     [rsp+78h+var_38], rax
0x1800061d2  mov     r14d, r9d
0x1800061d5  movzx   ebp, r8w
0x1800061d9  mov     esi, edx
0x1800061db  mov     rdi, rcx
0x1800061de  cmp     byte ptr [rcx], 0
0x1800061e1  jz      loc_180006291
0x1800061e7  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800061ec  test    al, al
0x1800061ee  jnz     loc_180006291
0x1800061f4  lea     rbx, [rdi+28h]
0x1800061f8  mov     rcx, rbx; SRWLock
0x1800061fb  call    cs:__imp_AcquireSRWLockExclusive
0x180006201  mov     [rsp+78h+var_50], rbx
0x180006206  xor     eax, eax
0x180006208  mov     [rsp+78h+var_42], ax
0x18000620d  mov     [rsp+78h+var_48], esi
0x180006211  mov     [rsp+78h+var_44], bp
0x180006216  mov     [rsp+78h+var_40], r14d
0x18000621b  lea     rcx, [rdi+0E8h]; this
0x180006222  lea     r8d, [rax+0Ch]; unsigned __int64
0x180006226  lea     rdx, [rsp+78h+var_48]; void *
0x18000622b  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180006230  nop
0x180006231  cmp     byte ptr [rdi+40h], 0
0x180006235  jnz     short loc_180006286
0x180006237  lea     rbx, [rdi+38h]
0x18000623b  cmp     qword ptr [rbx], 0
0x18000623f  jnz     short loc_180006273
0x180006241  lea     rcx, [rsp+78h+var_58]; this
0x180006246  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000624b  xor     r8d, r8d; pcbe
0x18000624e  mov     rdx, rdi; pv
0x180006251  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180006258  call    cs:__imp_CreateThreadpoolTimer
0x18000625e  mov     rdx, rax
0x180006261  mov     rcx, rbx
0x180006264  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180006269  lea     rcx, [rsp+78h+var_58]; this
0x18000626e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180006273  mov     r8d, 1388h
0x180006279  lea     rdx, [rdi+40h]
0x18000627d  mov     rcx, rbx
0x180006280  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180006285  nop
0x180006286  lea     rcx, [rsp+78h+var_50]
0x18000628b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180006290  nop
0x180006291  mov     rcx, [rsp+78h+var_38]
0x180006296  xor     rcx, rsp; StackCookie
0x180006299  call    __security_check_cookie
0x18000629e  add     rsp, 50h
0x1800062a2  pop     r14
0x1800062a4  pop     rdi
0x1800062a5  pop     rsi
0x1800062a6  pop     rbp
0x1800062a7  pop     rbx
0x1800062a8  retn
```
