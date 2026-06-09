# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180011934`
- end: `0x180011a17`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `227`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180022920`

## callees

- `0x18000fab0`
- `0x180011934`
- `0x180011b84`
- `0x180011ba4`
- `0x180011be8`
- `0x180011c0c`
- `0x180011c60`
- `0x180022eac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011970`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011970`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800119cc`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800119cc`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        char *pv,
        int a2,
        __int16 a3,
        int a4)
{
  PTP_TIMER ThreadpoolTimer; // rax
  char *v9; // [rsp+20h] [rbp-38h] BYREF
  int v10; // [rsp+28h] [rbp-30h] BYREF
  __int16 v11; // [rsp+2Ch] [rbp-2Ch]
  __int16 v12; // [rsp+2Eh] [rbp-2Ah]
  int v13; // [rsp+30h] [rbp-28h]
  char v14; // [rsp+60h] [rbp+8h] BYREF

  if ( *pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v9 = pv + 40;
    v12 = 0;
    v10 = a2;
    v11 = a3;
    v13 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 232), &v10, 0xCu);
    if ( !pv[64] )
    {
      if ( !*((_QWORD *)pv + 7) )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v14);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          pv + 56,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v14);
      }
      wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)pv + 7, pv + 64, 5000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  }
}

```

## disassembly

```asm
0x180011934  mov     [rsp+arg_8], rbx
0x180011939  mov     [rsp+arg_10], rbp
0x18001193e  push    rsi
0x18001193f  push    rdi
0x180011940  push    r14
0x180011942  sub     rsp, 40h
0x180011946  mov     esi, r9d
0x180011949  movzx   ebp, r8w
0x18001194d  mov     r14d, edx
0x180011950  mov     rdi, rcx
0x180011953  cmp     byte ptr [rcx], 0
0x180011956  jz      loc_180011A04
0x18001195c  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180011961  test    al, al
0x180011963  jnz     loc_180011A04
0x180011969  lea     rbx, [rdi+28h]
0x18001196d  mov     rcx, rbx; SRWLock
0x180011970  call    cs:__imp_AcquireSRWLockExclusive
0x180011976  mov     [rsp+58h+var_38], rbx
0x18001197b  xor     eax, eax
0x18001197d  mov     [rsp+58h+var_2A], ax
0x180011982  mov     [rsp+58h+var_30], r14d
0x180011987  mov     [rsp+58h+var_2C], bp
0x18001198c  mov     [rsp+58h+var_28], esi
0x180011990  lea     rcx, [rdi+0E8h]; this
0x180011997  lea     r8d, [rax+0Ch]; unsigned __int64
0x18001199b  lea     rdx, [rsp+58h+var_30]; void *
0x1800119a0  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800119a5  cmp     byte ptr [rdi+40h], 0
0x1800119a9  jnz     short loc_1800119F9
0x1800119ab  lea     rbx, [rdi+38h]
0x1800119af  cmp     qword ptr [rbx], 0
0x1800119b3  jnz     short loc_1800119E7
0x1800119b5  lea     rcx, [rsp+58h+arg_0]; this
0x1800119ba  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800119bf  xor     r8d, r8d; pcbe
0x1800119c2  mov     rdx, rdi; pv
0x1800119c5  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800119cc  call    cs:__imp_CreateThreadpoolTimer
0x1800119d2  mov     rdx, rax
0x1800119d5  mov     rcx, rbx
0x1800119d8  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800119dd  lea     rcx, [rsp+58h+arg_0]; this
0x1800119e2  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800119e7  mov     r8d, 1388h
0x1800119ed  lea     rdx, [rdi+40h]
0x1800119f1  mov     rcx, rbx
0x1800119f4  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1800119f9  lea     rcx, [rsp+58h+var_38]
0x1800119fe  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180011a03  nop
0x180011a04  mov     rbx, [rsp+58h+arg_8]
0x180011a09  mov     rbp, [rsp+58h+arg_10]
0x180011a0e  add     rsp, 40h
0x180011a12  pop     r14
0x180011a14  pop     rdi
0x180011a15  pop     rsi
0x180011a16  retn
```
