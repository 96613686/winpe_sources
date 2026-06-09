# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18001afcc`
- end: `0x18001b0b6`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `234`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18001c960`

## callees

- `0x180016650`
- `0x180016aac`
- `0x180016f4c`
- `0x180017c0c`
- `0x18001af98`
- `0x18001afcc`
- `0x18001d434`
- `0x18001d5b0`
- `0x18001d6c0`
- `0x18003e5c0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001b066`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001b066`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        struct _TP_TIMER **pv,
        int a2,
        __int16 a3,
        int a4)
{
  PTP_TIMER ThreadpoolTimer; // rax
  _BYTE v9[8]; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v10[8]; // [rsp+28h] [rbp-50h] BYREF
  int v11; // [rsp+30h] [rbp-48h] BYREF
  __int16 v12; // [rsp+34h] [rbp-44h]
  __int16 v13; // [rsp+36h] [rbp-42h]
  int v14; // [rsp+38h] [rbp-40h]

  if ( *(_BYTE *)pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    wil::srwlock::lock_exclusive(pv + 5, v10);
    v13 = 0;
    v11 = a2;
    v12 = a3;
    v14 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 29), &v11, 0xCu);
    if ( !*((_BYTE *)pv + 64) )
    {
      if ( !pv[7] )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v9);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          pv + 7,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v9);
      }
      wil::details::EnsureCoalescedTimer_SetTimer(pv + 7, (_BYTE *)pv + 64, 5000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v10);
  }
}

```

## disassembly

```asm
0x18001afcc  push    rbx
0x18001afce  push    rbp
0x18001afcf  push    rsi
0x18001afd0  push    rdi
0x18001afd1  sub     rsp, 58h
0x18001afd5  mov     rax, cs:__security_cookie
0x18001afdc  xor     rax, rsp
0x18001afdf  mov     [rsp+78h+var_38], rax
0x18001afe4  mov     ebp, r9d
0x18001afe7  movzx   esi, r8w
0x18001afeb  mov     ebx, edx
0x18001afed  mov     rdi, rcx
0x18001aff0  cmp     byte ptr [rcx], 0
0x18001aff3  jz      loc_18001B0A0
0x18001aff9  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18001affe  test    al, al
0x18001b000  jnz     loc_18001B0A0
0x18001b006  lea     rcx, [rdi+28h]
0x18001b00a  lea     rdx, [rsp+78h+var_50]
0x18001b00f  call    ?lock_exclusive@srwlock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::srwlock::lock_exclusive(void)
0x18001b014  nop
0x18001b015  xor     eax, eax
0x18001b017  mov     [rsp+78h+var_42], ax
0x18001b01c  mov     [rsp+78h+var_48], ebx
0x18001b020  mov     [rsp+78h+var_44], si
0x18001b025  mov     [rsp+78h+var_40], ebp
0x18001b029  lea     rcx, [rdi+0E8h]; this
0x18001b030  lea     r8d, [rax+0Ch]; unsigned __int64
0x18001b034  lea     rdx, [rsp+78h+var_48]; void *
0x18001b039  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001b03e  cmp     byte ptr [rdi+40h], 0
0x18001b042  jnz     short loc_18001B095
0x18001b044  lea     rbx, [rdi+38h]
0x18001b048  cmp     qword ptr [rbx], 0
0x18001b04c  jnz     short loc_18001B082
0x18001b04e  lea     rcx, [rsp+78h+var_58]; this
0x18001b053  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001b058  nop
0x18001b059  xor     r8d, r8d; pcbe
0x18001b05c  mov     rdx, rdi; pv
0x18001b05f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001b066  call    cs:__imp_CreateThreadpoolTimer
0x18001b06c  mov     rdx, rax
0x18001b06f  mov     rcx, rbx
0x18001b072  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001b077  nop
0x18001b078  lea     rcx, [rsp+78h+var_58]; this
0x18001b07d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001b082  mov     r8d, 1388h
0x18001b088  lea     rdx, [rdi+40h]
0x18001b08c  mov     rcx, rbx
0x18001b08f  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18001b094  nop
0x18001b095  lea     rcx, [rsp+78h+var_50]
0x18001b09a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001b09f  nop
0x18001b0a0  mov     rcx, [rsp+78h+var_38]
0x18001b0a5  xor     rcx, rsp; StackCookie
0x18001b0a8  call    __security_check_cookie
0x18001b0ad  add     rsp, 58h
0x18001b0b1  pop     rdi
0x18001b0b2  pop     rsi
0x18001b0b3  pop     rbp
0x18001b0b4  pop     rbx
0x18001b0b5  retn
```
