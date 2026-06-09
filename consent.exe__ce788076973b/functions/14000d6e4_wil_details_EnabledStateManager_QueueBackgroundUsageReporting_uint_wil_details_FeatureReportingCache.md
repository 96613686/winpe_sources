# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x14000d6e4`
- end: `0x14000d7b5`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `209`
- prototype: `void __fastcall(char *pv, int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x14001783c`

## callees

- `0x140005990`
- `0x140008b10`
- `0x14000a020`
- `0x14000a6cc`
- `0x14000d6e4`
- `0x14000e938`
- `0x14000e958`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000d713`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000d713`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000d7a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000d7a5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000d770`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000d770`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        char *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD v8[2]; // [rsp+20h] [rbp-38h] BYREF
  struct wil_details_FeatureReportingCache *v9; // [rsp+28h] [rbp-30h]
  char v10; // [rsp+60h] [rbp+8h] BYREF

  if ( *(_DWORD *)pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 1);
    if ( *(_DWORD *)pv )
    {
      if ( !wil::ProcessShutdownInProgress(v6) )
      {
        v8[0] = a2;
        v8[1] = 0;
        v9 = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 32), v8, 0x10u);
        if ( !pv[24] )
        {
          if ( !*((_QWORD *)pv + 2) )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&v10);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              pv + 16,
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v10);
          }
          wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)pv + 2, pv + 24, 300000);
        }
      }
    }
    if ( pv != (char *)-8LL )
      ReleaseSRWLockExclusive((PSRWLOCK)pv + 1);
  }
}

```

## disassembly

```asm
0x14000d6e4  push    rbx
0x14000d6e6  push    rbp
0x14000d6e7  push    rsi
0x14000d6e8  push    rdi
0x14000d6e9  sub     rsp, 38h
0x14000d6ed  mov     rsi, r8
0x14000d6f0  mov     ebp, edx
0x14000d6f2  mov     rbx, rcx
0x14000d6f5  mov     eax, [rcx]
0x14000d6f7  test    eax, eax
0x14000d6f9  jz      loc_14000D7AC
0x14000d6ff  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x14000d704  test    al, al
0x14000d706  jnz     loc_14000D7AC
0x14000d70c  lea     rdi, [rbx+8]
0x14000d710  mov     rcx, rdi; SRWLock
0x14000d713  call    cs:__imp_AcquireSRWLockExclusive
0x14000d719  mov     eax, [rbx]
0x14000d71b  test    eax, eax
0x14000d71d  jz      short loc_14000D79D
0x14000d71f  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x14000d724  test    al, al
0x14000d726  jnz     short loc_14000D79D
0x14000d728  mov     [rsp+58h+var_38], ebp
0x14000d72c  xor     eax, eax
0x14000d72e  mov     [rsp+58h+var_34], eax
0x14000d732  mov     [rsp+58h+var_30], rsi
0x14000d737  lea     rcx, [rbx+20h]; this
0x14000d73b  lea     r8d, [rax+10h]; unsigned __int64
0x14000d73f  lea     rdx, [rsp+58h+var_38]; void *
0x14000d744  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x14000d749  cmp     byte ptr [rbx+18h], 0
0x14000d74d  jnz     short loc_14000D79D
0x14000d74f  lea     rsi, [rbx+10h]
0x14000d753  cmp     qword ptr [rsi], 0
0x14000d757  jnz     short loc_14000D78B
0x14000d759  lea     rcx, [rsp+58h+arg_0]; this
0x14000d75e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14000d763  xor     r8d, r8d; pcbe
0x14000d766  mov     rdx, rbx; pv
0x14000d769  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14000d770  call    cs:__imp_CreateThreadpoolTimer
0x14000d776  mov     rdx, rax
0x14000d779  mov     rcx, rsi
0x14000d77c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x14000d781  lea     rcx, [rsp+58h+arg_0]; this
0x14000d786  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14000d78b  mov     r8d, 493E0h
0x14000d791  lea     rdx, [rbx+18h]
0x14000d795  mov     rcx, rsi
0x14000d798  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x14000d79d  test    rdi, rdi
0x14000d7a0  jz      short loc_14000D7AC
0x14000d7a2  mov     rcx, rdi; SRWLock
0x14000d7a5  call    cs:__imp_ReleaseSRWLockExclusive
0x14000d7ab  nop
0x14000d7ac  add     rsp, 38h
0x14000d7b0  pop     rdi
0x14000d7b1  pop     rsi
0x14000d7b2  pop     rbp
0x14000d7b3  pop     rbx
0x14000d7b4  retn
```
