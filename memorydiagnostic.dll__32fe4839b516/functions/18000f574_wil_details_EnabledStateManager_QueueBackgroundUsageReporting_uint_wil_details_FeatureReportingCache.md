# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18000f574`
- end: `0x18000f6d0`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `348`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180011070`

## callees

- `0x18000f574`
- `0x1800183b4`
- `0x180018824`
- `0x180024010`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x18000f64d`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000f64d`
- `KERNEL32!SetThreadpoolTimer` at `0x18000f697`
- `KERNEL32!SetThreadpoolTimer` at `0x18000f697`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000f5c5`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000f5c5`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000f6af`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000f6af`
- `KERNEL32!GetLastError` at `0x18000f632`
- `KERNEL32!GetLastError` at `0x18000f632`
- `KERNEL32!SetLastError` at `0x18000f666`
- `KERNEL32!SetLastError` at `0x18000f666`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  struct _TP_TIMER **v6; // r14
  DWORD LastError; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _TP_TIMER *v9; // rcx
  _DWORD Source[2]; // [rsp+20h] [rbp-28h] BYREF
  struct wil_details_FeatureReportingCache *v11; // [rsp+28h] [rbp-20h]
  struct _FILETIME pftDueTime; // [rsp+50h] [rbp+8h] BYREF

  if ( LODWORD(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 1);
    if ( LODWORD(pv->Ptr)
      && !wil::details::g_processShutdownInProgress
      && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
    {
      Source[0] = a2;
      Source[1] = 0;
      v11 = a3;
      wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[4], Source, 0x10u);
      v6 = (struct _TP_TIMER **)&pv[2];
      if ( !LOBYTE(pv[3].Ptr) )
      {
        if ( !*v6 )
        {
          LastError = GetLastError();
          ThreadpoolTimer = CreateThreadpoolTimer(
                              _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                              pv,
                              0);
          wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
            (struct _TP_TIMER **)&pv[2],
            ThreadpoolTimer);
          SetLastError(LastError);
        }
        v9 = *v6;
        if ( *v6 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v9, &pftDueTime, 0, 0x124F8u);
          LOBYTE(pv[3].Ptr) = 1;
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
0x18000f574  mov     [rsp+arg_8], rbx
0x18000f579  mov     [rsp+arg_10], rbp
0x18000f57e  push    rsi
0x18000f57f  push    rdi
0x18000f580  push    r14
0x18000f582  sub     rsp, 30h
0x18000f586  mov     rbx, r8
0x18000f589  mov     ebp, edx
0x18000f58b  mov     rdi, rcx
0x18000f58e  mov     eax, [rcx]
0x18000f590  test    eax, eax
0x18000f592  jz      loc_18000F6BC
0x18000f598  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000f59f  jnz     loc_18000F6BC
0x18000f5a5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000f5ac  test    rax, rax
0x18000f5af  jz      short loc_18000F5BE
0x18000f5b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5b6  test    al, al
0x18000f5b8  jnz     loc_18000F6BC
0x18000f5be  lea     rsi, [rdi+8]
0x18000f5c2  mov     rcx, rsi; SRWLock
0x18000f5c5  call    cs:__imp_AcquireSRWLockExclusive
0x18000f5cc  nop     dword ptr [rax+rax+00h]
0x18000f5d1  mov     eax, [rdi]
0x18000f5d3  test    eax, eax
0x18000f5d5  jz      loc_18000F6A7
0x18000f5db  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000f5e2  jnz     loc_18000F6A7
0x18000f5e8  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000f5ef  test    rax, rax
0x18000f5f2  jz      short loc_18000F601
0x18000f5f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5f9  test    al, al
0x18000f5fb  jnz     loc_18000F6A7
0x18000f601  mov     [rsp+48h+Source], ebp
0x18000f605  xor     eax, eax
0x18000f607  mov     [rsp+48h+var_24], eax
0x18000f60b  mov     [rsp+48h+var_20], rbx
0x18000f610  lea     rcx, [rdi+20h]; this
0x18000f614  lea     r8d, [rax+10h]; SourceSize
0x18000f618  lea     rdx, [rsp+48h+Source]; Source
0x18000f61d  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000f622  lea     r14, [rdi+10h]
0x18000f626  cmp     byte ptr [rdi+18h], 0
0x18000f62a  jnz     short loc_18000F6A7
0x18000f62c  cmp     qword ptr [r14], 0
0x18000f630  jnz     short loc_18000F672
0x18000f632  call    cs:__imp_GetLastError
0x18000f639  nop     dword ptr [rax+rax+00h]
0x18000f63e  mov     ebx, eax
0x18000f640  xor     r8d, r8d; pcbe
0x18000f643  mov     rdx, rdi; pv
0x18000f646  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000f64d  call    cs:__imp_CreateThreadpoolTimer
0x18000f654  nop     dword ptr [rax+rax+00h]
0x18000f659  mov     rdx, rax
0x18000f65c  mov     rcx, r14
0x18000f65f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000f664  mov     ecx, ebx; dwErrCode
0x18000f666  call    cs:__imp_SetLastError
0x18000f66d  nop     dword ptr [rax+rax+00h]
0x18000f672  mov     rcx, [r14]; pti
0x18000f675  test    rcx, rcx
0x18000f678  jz      short loc_18000F6A7
0x18000f67a  mov     rax, 0FFFFFFFF4D2FA200h
0x18000f684  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x18000f689  mov     r9d, 124F8h; msWindowLength
0x18000f68f  xor     r8d, r8d; msPeriod
0x18000f692  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x18000f697  call    cs:__imp_SetThreadpoolTimer
0x18000f69e  nop     dword ptr [rax+rax+00h]
0x18000f6a3  mov     byte ptr [rdi+18h], 1
0x18000f6a7  test    rsi, rsi
0x18000f6aa  jz      short loc_18000F6BC
0x18000f6ac  mov     rcx, rsi; SRWLock
0x18000f6af  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f6b6  nop     dword ptr [rax+rax+00h]
0x18000f6bb  nop
0x18000f6bc  mov     rbx, [rsp+48h+arg_8]
0x18000f6c1  mov     rbp, [rsp+48h+arg_10]
0x18000f6c6  add     rsp, 30h
0x18000f6ca  pop     r14
0x18000f6cc  pop     rdi
0x18000f6cd  pop     rsi
0x18000f6ce  retn
```
