# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180143f00`
- end: `0x180143fef`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `239`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180145910`

## callees

- `0x18012c76c`
- `0x1801417b4`
- `0x180141980`
- `0x180141c88`
- `0x180142378`
- `0x180143f00`
- `0x180145eb4`
- `0x180145fd4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180143f3c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180143f3c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180143f9e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180143f9e`

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
0x180143f00  mov     [rsp+arg_8], rbx
0x180143f05  mov     [rsp+arg_10], rbp
0x180143f0a  push    rsi
0x180143f0b  push    rdi
0x180143f0c  push    r14
0x180143f0e  sub     rsp, 40h
0x180143f12  cmp     byte ptr [rcx], 0
0x180143f15  mov     esi, r9d
0x180143f18  movzx   ebp, r8w
0x180143f1c  mov     r14d, edx
0x180143f1f  mov     rdi, rcx
0x180143f22  jz      loc_180143FDB
0x180143f28  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180143f2d  test    al, al
0x180143f2f  jnz     loc_180143FDB
0x180143f35  lea     rbx, [rdi+28h]
0x180143f39  mov     rcx, rbx; SRWLock
0x180143f3c  call    cs:__imp_AcquireSRWLockExclusive
0x180143f43  nop     dword ptr [rax+rax+00h]
0x180143f48  xor     eax, eax
0x180143f4a  mov     [rsp+58h+var_38], rbx
0x180143f4f  lea     rcx, [rdi+0E8h]; this
0x180143f56  mov     [rsp+58h+var_2A], ax
0x180143f5b  lea     rdx, [rsp+58h+var_30]; void *
0x180143f60  mov     [rsp+58h+var_30], r14d
0x180143f65  mov     [rsp+58h+var_2C], bp
0x180143f6a  lea     r8d, [rax+0Ch]; unsigned __int64
0x180143f6e  mov     [rsp+58h+var_28], esi
0x180143f72  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180143f77  cmp     byte ptr [rdi+40h], 0
0x180143f7b  jnz     short loc_180143FD1
0x180143f7d  lea     rbx, [rdi+38h]
0x180143f81  cmp     qword ptr [rbx], 0
0x180143f85  jnz     short loc_180143FBF
0x180143f87  lea     rcx, [rsp+58h+arg_0]; this
0x180143f8c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180143f91  xor     r8d, r8d; pcbe
0x180143f94  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180143f9b  mov     rdx, rdi; pv
0x180143f9e  call    cs:__imp_CreateThreadpoolTimer
0x180143fa5  nop     dword ptr [rax+rax+00h]
0x180143faa  mov     rdx, rax
0x180143fad  mov     rcx, rbx
0x180143fb0  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180143fb5  lea     rcx, [rsp+58h+arg_0]; this
0x180143fba  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180143fbf  mov     r8d, 1388h
0x180143fc5  lea     rdx, [rdi+40h]
0x180143fc9  mov     rcx, rbx
0x180143fcc  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180143fd1  lea     rcx, [rsp+58h+var_38]
0x180143fd6  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180143fdb  mov     rbx, [rsp+58h+arg_8]
0x180143fe0  mov     rbp, [rsp+58h+arg_10]
0x180143fe5  add     rsp, 40h
0x180143fe9  pop     r14
0x180143feb  pop     rdi
0x180143fec  pop     rsi
0x180143fed  retn
```
