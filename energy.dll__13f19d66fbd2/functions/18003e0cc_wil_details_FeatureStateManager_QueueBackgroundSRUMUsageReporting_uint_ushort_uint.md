# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18003e0cc`
- end: `0x18003e1af`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `227`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180055110`

## callees

- `0x18003e0cc`
- `0x18003e280`
- `0x18003e2a0`
- `0x18003e2e4`
- `0x18003e304`
- `0x18003e328`
- `0x18003e450`
- `0x180055684`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003e108`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003e108`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003e164`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003e164`

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
0x18003e0cc  mov     [rsp+arg_8], rbx
0x18003e0d1  mov     [rsp+arg_10], rbp
0x18003e0d6  push    rsi
0x18003e0d7  push    rdi
0x18003e0d8  push    r14
0x18003e0da  sub     rsp, 40h
0x18003e0de  mov     esi, r9d
0x18003e0e1  movzx   ebp, r8w
0x18003e0e5  mov     r14d, edx
0x18003e0e8  mov     rdi, rcx
0x18003e0eb  cmp     byte ptr [rcx], 0
0x18003e0ee  jz      loc_18003E19C
0x18003e0f4  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18003e0f9  test    al, al
0x18003e0fb  jnz     loc_18003E19C
0x18003e101  lea     rbx, [rdi+28h]
0x18003e105  mov     rcx, rbx; SRWLock
0x18003e108  call    cs:__imp_AcquireSRWLockExclusive
0x18003e10e  mov     [rsp+58h+var_38], rbx
0x18003e113  xor     eax, eax
0x18003e115  mov     [rsp+58h+var_2A], ax
0x18003e11a  mov     [rsp+58h+var_30], r14d
0x18003e11f  mov     [rsp+58h+var_2C], bp
0x18003e124  mov     [rsp+58h+var_28], esi
0x18003e128  lea     rcx, [rdi+0E8h]; this
0x18003e12f  lea     r8d, [rax+0Ch]; unsigned __int64
0x18003e133  lea     rdx, [rsp+58h+var_30]; void *
0x18003e138  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18003e13d  cmp     byte ptr [rdi+40h], 0
0x18003e141  jnz     short loc_18003E191
0x18003e143  lea     rbx, [rdi+38h]
0x18003e147  cmp     qword ptr [rbx], 0
0x18003e14b  jnz     short loc_18003E17F
0x18003e14d  lea     rcx, [rsp+58h+arg_0]; this
0x18003e152  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18003e157  xor     r8d, r8d; pcbe
0x18003e15a  mov     rdx, rdi; pv
0x18003e15d  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18003e164  call    cs:__imp_CreateThreadpoolTimer
0x18003e16a  mov     rdx, rax
0x18003e16d  mov     rcx, rbx
0x18003e170  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18003e175  lea     rcx, [rsp+58h+arg_0]; this
0x18003e17a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18003e17f  mov     r8d, 1388h
0x18003e185  lea     rdx, [rdi+40h]
0x18003e189  mov     rcx, rbx
0x18003e18c  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18003e191  lea     rcx, [rsp+58h+var_38]
0x18003e196  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003e19b  nop
0x18003e19c  mov     rbx, [rsp+58h+arg_8]
0x18003e1a1  mov     rbp, [rsp+58h+arg_10]
0x18003e1a6  add     rsp, 40h
0x18003e1aa  pop     r14
0x18003e1ac  pop     rdi
0x18003e1ad  pop     rsi
0x18003e1ae  retn
```
