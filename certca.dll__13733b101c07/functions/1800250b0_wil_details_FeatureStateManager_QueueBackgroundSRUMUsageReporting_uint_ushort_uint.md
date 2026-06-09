# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1800250b0`
- end: `0x18002519a`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `234`
- prototype: `void __fastcall(char *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180026660`

## callees

- `0x18001c618`
- `0x18001d374`
- `0x1800230a8`
- `0x18002376c`
- `0x180023d80`
- `0x18002507c`
- `0x1800250b0`
- `0x180026b20`
- `0x180026c30`
- `0x1800382c0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002514a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002514a`

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
    wil::srwlock::lock_exclusive((RTL_SRWLOCK *)pv + 5, &v10);
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
0x1800250b0  push    rbx
0x1800250b2  push    rbp
0x1800250b3  push    rsi
0x1800250b4  push    rdi
0x1800250b5  sub     rsp, 58h
0x1800250b9  mov     rax, cs:__security_cookie
0x1800250c0  xor     rax, rsp
0x1800250c3  mov     [rsp+78h+var_38], rax
0x1800250c8  mov     ebp, r9d
0x1800250cb  movzx   esi, r8w
0x1800250cf  mov     ebx, edx
0x1800250d1  mov     rdi, rcx
0x1800250d4  cmp     byte ptr [rcx], 0
0x1800250d7  jz      loc_180025184
0x1800250dd  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800250e2  test    al, al
0x1800250e4  jnz     loc_180025184
0x1800250ea  lea     rcx, [rdi+28h]
0x1800250ee  lea     rdx, [rsp+78h+var_50]
0x1800250f3  call    ?lock_exclusive@srwlock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::srwlock::lock_exclusive(void)
0x1800250f8  nop
0x1800250f9  xor     eax, eax
0x1800250fb  mov     [rsp+78h+var_42], ax
0x180025100  mov     [rsp+78h+var_48], ebx
0x180025104  mov     [rsp+78h+var_44], si
0x180025109  mov     [rsp+78h+var_40], ebp
0x18002510d  lea     rcx, [rdi+0E8h]; this
0x180025114  lea     r8d, [rax+0Ch]; unsigned __int64
0x180025118  lea     rdx, [rsp+78h+var_48]; void *
0x18002511d  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180025122  cmp     byte ptr [rdi+40h], 0
0x180025126  jnz     short loc_180025179
0x180025128  lea     rbx, [rdi+38h]
0x18002512c  cmp     qword ptr [rbx], 0
0x180025130  jnz     short loc_180025166
0x180025132  lea     rcx, [rsp+78h+var_58]; this
0x180025137  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002513c  nop
0x18002513d  xor     r8d, r8d; pcbe
0x180025140  mov     rdx, rdi; pv
0x180025143  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18002514a  call    cs:__imp_CreateThreadpoolTimer
0x180025150  mov     rdx, rax
0x180025153  mov     rcx, rbx
0x180025156  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18002515b  nop
0x18002515c  lea     rcx, [rsp+78h+var_58]; this
0x180025161  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180025166  mov     r8d, 1388h
0x18002516c  lea     rdx, [rdi+40h]
0x180025170  mov     rcx, rbx
0x180025173  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180025178  nop
0x180025179  lea     rcx, [rsp+78h+var_50]
0x18002517e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180025183  nop
0x180025184  mov     rcx, [rsp+78h+var_38]
0x180025189  xor     rcx, rsp; StackCookie
0x18002518c  call    __security_check_cookie
0x180025191  add     rsp, 58h
0x180025195  pop     rdi
0x180025196  pop     rsi
0x180025197  pop     rbp
0x180025198  pop     rbx
0x180025199  retn
```
