# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18001a03c`
- end: `0x18001a12a`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `238`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180031350`

## callees

- `0x18001a03c`
- `0x18001a1f8`
- `0x18001a218`
- `0x18001a25c`
- `0x18001a27c`
- `0x18001a2a0`
- `0x18001a3c8`
- `0x18001d8e0`
- `0x180031814`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a07f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a07f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001a0db`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001a0db`

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
0x18001a03c  push    rbx
0x18001a03e  push    rbp
0x18001a03f  push    rsi
0x18001a040  push    rdi
0x18001a041  push    r14
0x18001a043  sub     rsp, 50h
0x18001a047  mov     rax, cs:__security_cookie
0x18001a04e  xor     rax, rsp
0x18001a051  mov     [rsp+78h+var_38], rax
0x18001a056  cmp     byte ptr [rcx], 0
0x18001a059  mov     r14d, r9d
0x18001a05c  movzx   ebp, r8w
0x18001a060  mov     esi, edx
0x18001a062  mov     rdi, rcx
0x18001a065  jz      loc_18001A112
0x18001a06b  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18001a070  test    al, al
0x18001a072  jnz     loc_18001A112
0x18001a078  lea     rbx, [rdi+28h]
0x18001a07c  mov     rcx, rbx; SRWLock
0x18001a07f  call    cs:__imp_AcquireSRWLockExclusive
0x18001a085  xor     eax, eax
0x18001a087  mov     [rsp+78h+var_50], rbx
0x18001a08c  lea     rcx, [rdi+0E8h]; this
0x18001a093  mov     [rsp+78h+var_42], ax
0x18001a098  lea     rdx, [rsp+78h+var_48]; void *
0x18001a09d  mov     [rsp+78h+var_48], esi
0x18001a0a1  mov     [rsp+78h+var_44], bp
0x18001a0a6  lea     r8d, [rax+0Ch]; unsigned __int64
0x18001a0aa  mov     [rsp+78h+var_40], r14d
0x18001a0af  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001a0b4  cmp     byte ptr [rdi+40h], 0
0x18001a0b8  jnz     short loc_18001A108
0x18001a0ba  lea     rbx, [rdi+38h]
0x18001a0be  cmp     qword ptr [rbx], 0
0x18001a0c2  jnz     short loc_18001A0F6
0x18001a0c4  lea     rcx, [rsp+78h+var_58]; this
0x18001a0c9  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001a0ce  xor     r8d, r8d; pcbe
0x18001a0d1  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001a0d8  mov     rdx, rdi; pv
0x18001a0db  call    cs:__imp_CreateThreadpoolTimer
0x18001a0e1  mov     rdx, rax
0x18001a0e4  mov     rcx, rbx
0x18001a0e7  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001a0ec  lea     rcx, [rsp+78h+var_58]; this
0x18001a0f1  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001a0f6  mov     r8d, 1388h
0x18001a0fc  lea     rdx, [rdi+40h]
0x18001a100  mov     rcx, rbx
0x18001a103  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18001a108  lea     rcx, [rsp+78h+var_50]
0x18001a10d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001a112  mov     rcx, [rsp+78h+var_38]
0x18001a117  xor     rcx, rsp; StackCookie
0x18001a11a  call    __security_check_cookie
0x18001a11f  add     rsp, 50h
0x18001a123  pop     r14
0x18001a125  pop     rdi
0x18001a126  pop     rsi
0x18001a127  pop     rbp
0x18001a128  pop     rbx
0x18001a129  retn
```
