# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x1800157d8`
- end: `0x1800158bb`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `227`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180015b50`

## callees

- `0x180009ff0`
- `0x18000a118`
- `0x18000b5ec`
- `0x18000dbf4`
- `0x18000df68`
- `0x18000e5d4`
- `0x18001201c`
- `0x1800157d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015814`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015814`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180015876`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180015876`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD v8[2]; // [rsp+20h] [rbp-38h] BYREF
  struct wil_details_FeatureReportingCache *v9; // [rsp+28h] [rbp-30h]
  _QWORD v10[5]; // [rsp+30h] [rbp-28h] BYREF

  v10[1] = -2;
  if ( LODWORD(pv->Ptr) && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive(pv + 1);
    v10[0] = pv + 1;
    if ( LODWORD(pv->Ptr) )
    {
      if ( !wil::ProcessShutdownInProgress(v6) )
      {
        v8[0] = a2;
        v8[1] = 0;
        v9 = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[4], v8, 0x10u);
        if ( !LOBYTE(pv[3].Ptr) )
        {
          if ( !pv[2].Ptr )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)v8);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              &pv[2],
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)v8);
          }
          wil::details::EnsureCoalescedTimer_SetTimer(&pv[2], &pv[3], 300000);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v10);
  }
}

```

## disassembly

```asm
0x1800157d8  push    rbp
0x1800157da  push    rsi
0x1800157db  push    rdi
0x1800157dc  sub     rsp, 40h
0x1800157e0  mov     [rsp+58h+var_20], 0FFFFFFFFFFFFFFFEh
0x1800157e9  mov     [rsp+58h+arg_18], rbx
0x1800157ee  mov     rbp, r8
0x1800157f1  mov     esi, edx
0x1800157f3  mov     rdi, rcx
0x1800157f6  mov     eax, [rcx]
0x1800157f8  test    eax, eax
0x1800157fa  jz      loc_1800158AE
0x180015800  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180015805  test    al, al
0x180015807  jnz     loc_1800158AE
0x18001580d  lea     rbx, [rdi+8]
0x180015811  mov     rcx, rbx; SRWLock
0x180015814  call    cs:__imp_AcquireSRWLockExclusive
0x18001581a  mov     [rsp+58h+var_28], rbx
0x18001581f  mov     eax, [rdi]
0x180015821  test    eax, eax
0x180015823  jz      short loc_1800158A3
0x180015825  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18001582a  test    al, al
0x18001582c  jnz     short loc_1800158A3
0x18001582e  mov     [rsp+58h+var_38], esi
0x180015832  xor     eax, eax
0x180015834  mov     [rsp+58h+var_34], eax
0x180015838  mov     [rsp+58h+var_30], rbp
0x18001583d  lea     rcx, [rdi+20h]; this
0x180015841  lea     r8d, [rax+10h]; unsigned __int64
0x180015845  lea     rdx, [rsp+58h+var_38]; void *
0x18001584a  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001584f  cmp     byte ptr [rdi+18h], 0
0x180015853  jnz     short loc_1800158A3
0x180015855  lea     rbx, [rdi+10h]
0x180015859  cmp     qword ptr [rbx], 0
0x18001585d  jnz     short loc_180015891
0x18001585f  lea     rcx, [rsp+58h+var_38]; this
0x180015864  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180015869  xor     r8d, r8d; pcbe
0x18001586c  mov     rdx, rdi; pv
0x18001586f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180015876  call    cs:__imp_CreateThreadpoolTimer
0x18001587c  mov     rdx, rax
0x18001587f  mov     rcx, rbx
0x180015882  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180015887  lea     rcx, [rsp+58h+var_38]; this
0x18001588c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180015891  mov     r8d, 493E0h
0x180015897  lea     rdx, [rdi+18h]
0x18001589b  mov     rcx, rbx
0x18001589e  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1800158a3  lea     rcx, [rsp+58h+var_28]
0x1800158a8  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800158ad  nop
0x1800158ae  mov     rbx, [rsp+58h+arg_18]
0x1800158b3  add     rsp, 40h
0x1800158b7  pop     rdi
0x1800158b8  pop     rsi
0x1800158b9  pop     rbp
0x1800158ba  retn
```
