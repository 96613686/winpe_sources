# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x1800329e8`
- end: `0x180032ac1`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `217`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180032410`
- `0x18003256c`

## callees

- `0x1800329e8`
- `0x18003c298`
- `0x18003d080`
- `0x18003d700`
- `0x18003dbb0`
- `0x180052c04`
- `0x180058c1c`
- `0x18005b0c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180032a1a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180032a1a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180032a7c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180032a7c`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD Src[2]; // [rsp+20h] [rbp-28h] BYREF
  struct wil_details_FeatureReportingCache *v9; // [rsp+28h] [rbp-20h]
  char v10; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v11; // [rsp+68h] [rbp+20h] BYREF

  if ( LODWORD(pv->Ptr) && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive(pv + 1);
    v11 = pv + 1;
    if ( LODWORD(pv->Ptr) )
    {
      if ( !wil::ProcessShutdownInProgress(v6) )
      {
        Src[0] = a2;
        Src[1] = 0;
        v9 = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[4], Src, 0x10u);
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
    CSRWLock::CWriterLock::~CWriterLock((CSRWLock::CWriterLock *)&v11);
  }
}

```

## disassembly

```asm
0x1800329e8  mov     [rsp+arg_8], rbx
0x1800329ed  push    rbp
0x1800329ee  push    rsi
0x1800329ef  push    rdi
0x1800329f0  sub     rsp, 30h
0x1800329f4  mov     rsi, r8
0x1800329f7  mov     ebp, edx
0x1800329f9  mov     rdi, rcx
0x1800329fc  mov     eax, [rcx]
0x1800329fe  test    eax, eax
0x180032a00  jz      loc_180032AB4
0x180032a06  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180032a0b  test    al, al
0x180032a0d  jnz     loc_180032AB4
0x180032a13  lea     rbx, [rdi+8]
0x180032a17  mov     rcx, rbx; SRWLock
0x180032a1a  call    cs:__imp_AcquireSRWLockExclusive
0x180032a20  mov     [rsp+48h+arg_18], rbx
0x180032a25  mov     eax, [rdi]
0x180032a27  test    eax, eax
0x180032a29  jz      short loc_180032AA9
0x180032a2b  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180032a30  test    al, al
0x180032a32  jnz     short loc_180032AA9
0x180032a34  mov     [rsp+48h+Src], ebp
0x180032a38  xor     eax, eax
0x180032a3a  mov     [rsp+48h+var_24], eax
0x180032a3e  mov     [rsp+48h+var_20], rsi
0x180032a43  lea     rcx, [rdi+20h]; this
0x180032a47  lea     r8d, [rax+10h]; Size
0x180032a4b  lea     rdx, [rsp+48h+Src]; Src
0x180032a50  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180032a55  cmp     byte ptr [rdi+18h], 0
0x180032a59  jnz     short loc_180032AA9
0x180032a5b  lea     rbx, [rdi+10h]
0x180032a5f  cmp     qword ptr [rbx], 0
0x180032a63  jnz     short loc_180032A97
0x180032a65  lea     rcx, [rsp+48h+arg_0]; this
0x180032a6a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180032a6f  xor     r8d, r8d; pcbe
0x180032a72  mov     rdx, rdi; pv
0x180032a75  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180032a7c  call    cs:__imp_CreateThreadpoolTimer
0x180032a82  mov     rdx, rax
0x180032a85  mov     rcx, rbx
0x180032a88  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180032a8d  lea     rcx, [rsp+48h+arg_0]; this
0x180032a92  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180032a97  mov     r8d, 493E0h
0x180032a9d  lea     rdx, [rdi+18h]
0x180032aa1  mov     rcx, rbx
0x180032aa4  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180032aa9  lea     rcx, [rsp+48h+arg_18]; this
0x180032aae  call    ??1CWriterLock@CSRWLock@@QEAA@XZ; CSRWLock::CWriterLock::~CWriterLock(void)
0x180032ab3  nop
0x180032ab4  mov     rbx, [rsp+48h+arg_8]
0x180032ab9  add     rsp, 30h
0x180032abd  pop     rdi
0x180032abe  pop     rsi
0x180032abf  pop     rbp
0x180032ac0  retn
```
