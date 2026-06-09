# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180031248`
- end: `0x180031319`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `209`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180033c68`

## callees

- `0x180020694`
- `0x180020c38`
- `0x180030e58`
- `0x180030e78`
- `0x180030ebc`
- `0x1800310a0`
- `0x180031248`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180031277`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180031277`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031309`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031309`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800312d4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800312d4`

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
  char v10; // [rsp+60h] [rbp+8h] BYREF

  if ( LODWORD(pv->Ptr) && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive(pv + 1);
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
            wil::last_error_context::last_error_context((wil::last_error_context *)&v10);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              &pv[2],
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v10);
          }
          wil::details::EnsureCoalescedTimer_SetTimer(&pv[2], &pv[3], 300000);
        }
      }
    }
    if ( pv != (RTL_SRWLOCK *)-8LL )
      ReleaseSRWLockExclusive(pv + 1);
  }
}

```

## disassembly

```asm
0x180031248  push    rbx
0x18003124a  push    rbp
0x18003124b  push    rsi
0x18003124c  push    rdi
0x18003124d  sub     rsp, 38h
0x180031251  mov     rsi, r8
0x180031254  mov     ebp, edx
0x180031256  mov     rbx, rcx
0x180031259  mov     eax, [rcx]
0x18003125b  test    eax, eax
0x18003125d  jz      loc_180031310
0x180031263  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180031268  test    al, al
0x18003126a  jnz     loc_180031310
0x180031270  lea     rdi, [rbx+8]
0x180031274  mov     rcx, rdi; SRWLock
0x180031277  call    cs:__imp_AcquireSRWLockExclusive
0x18003127d  mov     eax, [rbx]
0x18003127f  test    eax, eax
0x180031281  jz      short loc_180031301
0x180031283  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180031288  test    al, al
0x18003128a  jnz     short loc_180031301
0x18003128c  mov     [rsp+58h+var_38], ebp
0x180031290  xor     eax, eax
0x180031292  mov     [rsp+58h+var_34], eax
0x180031296  mov     [rsp+58h+var_30], rsi
0x18003129b  lea     rcx, [rbx+20h]; this
0x18003129f  lea     r8d, [rax+10h]; unsigned __int64
0x1800312a3  lea     rdx, [rsp+58h+var_38]; void *
0x1800312a8  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800312ad  cmp     byte ptr [rbx+18h], 0
0x1800312b1  jnz     short loc_180031301
0x1800312b3  lea     rsi, [rbx+10h]
0x1800312b7  cmp     qword ptr [rsi], 0
0x1800312bb  jnz     short loc_1800312EF
0x1800312bd  lea     rcx, [rsp+58h+arg_0]; this
0x1800312c2  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800312c7  xor     r8d, r8d; pcbe
0x1800312ca  mov     rdx, rbx; pv
0x1800312cd  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800312d4  call    cs:__imp_CreateThreadpoolTimer
0x1800312da  mov     rdx, rax
0x1800312dd  mov     rcx, rsi
0x1800312e0  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800312e5  lea     rcx, [rsp+58h+arg_0]; this
0x1800312ea  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800312ef  mov     r8d, 493E0h
0x1800312f5  lea     rdx, [rbx+18h]
0x1800312f9  mov     rcx, rsi
0x1800312fc  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180031301  test    rdi, rdi
0x180031304  jz      short loc_180031310
0x180031306  mov     rcx, rdi; SRWLock
0x180031309  call    cs:__imp_ReleaseSRWLockExclusive
0x18003130f  nop
0x180031310  add     rsp, 38h
0x180031314  pop     rdi
0x180031315  pop     rsi
0x180031316  pop     rbp
0x180031317  pop     rbx
0x180031318  retn
```
