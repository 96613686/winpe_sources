# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x140019638`
- end: `0x140019729`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `241`
- prototype: `void __fastcall(char *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x14001b140`

## callees

- `0x140016e8c`
- `0x140017254`
- `0x140017578`
- `0x140017b80`
- `0x140019604`
- `0x140019638`
- `0x14001bc5c`
- `0x14001bd6c`
- `0x14001cf00`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x1400196d8`
- `KERNEL32!CreateThreadpoolTimer` at `0x1400196d8`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14001967b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14001967b`

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
0x140019638  push    rbx
0x14001963a  push    rbp
0x14001963b  push    rsi
0x14001963c  push    rdi
0x14001963d  push    r14
0x14001963f  sub     rsp, 50h
0x140019643  mov     rax, cs:__security_cookie
0x14001964a  xor     rax, rsp
0x14001964d  mov     [rsp+78h+var_38], rax
0x140019652  mov     r14d, r9d
0x140019655  movzx   ebp, r8w
0x140019659  mov     esi, edx
0x14001965b  mov     rdi, rcx
0x14001965e  cmp     byte ptr [rcx], 0
0x140019661  jz      loc_140019711
0x140019667  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x14001966c  test    al, al
0x14001966e  jnz     loc_140019711
0x140019674  lea     rbx, [rdi+28h]
0x140019678  mov     rcx, rbx; SRWLock
0x14001967b  call    cs:__imp_AcquireSRWLockExclusive
0x140019681  mov     [rsp+78h+var_50], rbx
0x140019686  xor     eax, eax
0x140019688  mov     [rsp+78h+var_42], ax
0x14001968d  mov     [rsp+78h+var_48], esi
0x140019691  mov     [rsp+78h+var_44], bp
0x140019696  mov     [rsp+78h+var_40], r14d
0x14001969b  lea     rcx, [rdi+0E8h]; this
0x1400196a2  lea     r8d, [rax+0Ch]; unsigned __int64
0x1400196a6  lea     rdx, [rsp+78h+var_48]; void *
0x1400196ab  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1400196b0  nop
0x1400196b1  cmp     byte ptr [rdi+40h], 0
0x1400196b5  jnz     short loc_140019706
0x1400196b7  lea     rbx, [rdi+38h]
0x1400196bb  cmp     qword ptr [rbx], 0
0x1400196bf  jnz     short loc_1400196F3
0x1400196c1  lea     rcx, [rsp+78h+var_58]; this
0x1400196c6  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1400196cb  xor     r8d, r8d; pcbe
0x1400196ce  mov     rdx, rdi; pv
0x1400196d1  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1400196d8  call    cs:__imp_CreateThreadpoolTimer
0x1400196de  mov     rdx, rax
0x1400196e1  mov     rcx, rbx
0x1400196e4  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1400196e9  lea     rcx, [rsp+78h+var_58]; this
0x1400196ee  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1400196f3  mov     r8d, 1388h
0x1400196f9  lea     rdx, [rdi+40h]
0x1400196fd  mov     rcx, rbx
0x140019700  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x140019705  nop
0x140019706  lea     rcx, [rsp+78h+var_50]
0x14001970b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140019710  nop
0x140019711  mov     rcx, [rsp+78h+var_38]
0x140019716  xor     rcx, rsp; StackCookie
0x140019719  call    __security_check_cookie
0x14001971e  add     rsp, 50h
0x140019722  pop     r14
0x140019724  pop     rdi
0x140019725  pop     rsi
0x140019726  pop     rbp
0x140019727  pop     rbx
0x140019728  retn
```
