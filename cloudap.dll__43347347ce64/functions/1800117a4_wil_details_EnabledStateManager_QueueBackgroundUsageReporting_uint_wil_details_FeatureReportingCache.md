# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x1800117a4`
- end: `0x180011875`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `209`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180011294`
- `0x180011520`

## callees

- `0x1800117a4`
- `0x18002cb90`
- `0x18002cbc8`
- `0x18002cc0c`
- `0x180032fcc`
- `0x18003b944`
- `0x18003b964`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011865`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011865`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800117d3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800117d3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180011830`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180011830`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        char *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD Src[2]; // [rsp+20h] [rbp-38h] BYREF
  struct wil_details_FeatureReportingCache *v9; // [rsp+28h] [rbp-30h]
  char v10; // [rsp+60h] [rbp+8h] BYREF

  if ( *(_DWORD *)pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 1);
    if ( *(_DWORD *)pv )
    {
      if ( !wil::ProcessShutdownInProgress(v6) )
      {
        Src[0] = a2;
        Src[1] = 0;
        v9 = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 32), Src, 0x10u);
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
0x1800117a4  push    rbx
0x1800117a6  push    rbp
0x1800117a7  push    rsi
0x1800117a8  push    rdi
0x1800117a9  sub     rsp, 38h
0x1800117ad  mov     rsi, r8
0x1800117b0  mov     ebp, edx
0x1800117b2  mov     rbx, rcx
0x1800117b5  mov     eax, [rcx]
0x1800117b7  test    eax, eax
0x1800117b9  jz      loc_18001186C
0x1800117bf  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800117c4  test    al, al
0x1800117c6  jnz     loc_18001186C
0x1800117cc  lea     rdi, [rbx+8]
0x1800117d0  mov     rcx, rdi; SRWLock
0x1800117d3  call    cs:__imp_AcquireSRWLockExclusive
0x1800117d9  mov     eax, [rbx]
0x1800117db  test    eax, eax
0x1800117dd  jz      short loc_18001185D
0x1800117df  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800117e4  test    al, al
0x1800117e6  jnz     short loc_18001185D
0x1800117e8  mov     [rsp+58h+Src], ebp
0x1800117ec  xor     eax, eax
0x1800117ee  mov     [rsp+58h+var_34], eax
0x1800117f2  mov     [rsp+58h+var_30], rsi
0x1800117f7  lea     rcx, [rbx+20h]; this
0x1800117fb  lea     r8d, [rax+10h]; Size
0x1800117ff  lea     rdx, [rsp+58h+Src]; Src
0x180011804  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180011809  cmp     byte ptr [rbx+18h], 0
0x18001180d  jnz     short loc_18001185D
0x18001180f  lea     rsi, [rbx+10h]
0x180011813  cmp     qword ptr [rsi], 0
0x180011817  jnz     short loc_18001184B
0x180011819  lea     rcx, [rsp+58h+arg_0]; this
0x18001181e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180011823  xor     r8d, r8d; pcbe
0x180011826  mov     rdx, rbx; pv
0x180011829  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180011830  call    cs:__imp_CreateThreadpoolTimer
0x180011836  mov     rdx, rax
0x180011839  mov     rcx, rsi
0x18001183c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180011841  lea     rcx, [rsp+58h+arg_0]; this
0x180011846  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001184b  mov     r8d, 493E0h
0x180011851  lea     rdx, [rbx+18h]
0x180011855  mov     rcx, rsi
0x180011858  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18001185d  test    rdi, rdi
0x180011860  jz      short loc_18001186C
0x180011862  mov     rcx, rdi; SRWLock
0x180011865  call    cs:__imp_ReleaseSRWLockExclusive
0x18001186b  nop
0x18001186c  add     rsp, 38h
0x180011870  pop     rdi
0x180011871  pop     rsi
0x180011872  pop     rbp
0x180011873  pop     rbx
0x180011874  retn
```
