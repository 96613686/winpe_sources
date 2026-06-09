# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x1800106a0`
- end: `0x1800107fc`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `348`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800108a8`

## callees

- `0x180009abc`
- `0x180009c50`
- `0x1800106a0`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800107db`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800107db`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800106f1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800106f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001075e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001075e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010792`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010792`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180010779`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180010779`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800107c3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800107c3`

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
0x1800106a0  mov     [rsp+arg_8], rbx
0x1800106a5  mov     [rsp+arg_10], rbp
0x1800106aa  push    rsi
0x1800106ab  push    rdi
0x1800106ac  push    r14
0x1800106ae  sub     rsp, 30h
0x1800106b2  mov     rbx, r8
0x1800106b5  mov     ebp, edx
0x1800106b7  mov     rdi, rcx
0x1800106ba  mov     eax, [rcx]
0x1800106bc  test    eax, eax
0x1800106be  jz      loc_1800107E8
0x1800106c4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800106cb  jnz     loc_1800107E8
0x1800106d1  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800106d8  test    rax, rax
0x1800106db  jz      short loc_1800106EA
0x1800106dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106e2  test    al, al
0x1800106e4  jnz     loc_1800107E8
0x1800106ea  lea     rsi, [rdi+8]
0x1800106ee  mov     rcx, rsi; SRWLock
0x1800106f1  call    cs:__imp_AcquireSRWLockExclusive
0x1800106f8  nop     dword ptr [rax+rax+00h]
0x1800106fd  mov     eax, [rdi]
0x1800106ff  test    eax, eax
0x180010701  jz      loc_1800107D3
0x180010707  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001070e  jnz     loc_1800107D3
0x180010714  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001071b  test    rax, rax
0x18001071e  jz      short loc_18001072D
0x180010720  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010725  test    al, al
0x180010727  jnz     loc_1800107D3
0x18001072d  mov     [rsp+48h+Source], ebp
0x180010731  xor     eax, eax
0x180010733  mov     [rsp+48h+var_24], eax
0x180010737  mov     [rsp+48h+var_20], rbx
0x18001073c  lea     rcx, [rdi+20h]; this
0x180010740  lea     r8d, [rax+10h]; SourceSize
0x180010744  lea     rdx, [rsp+48h+Source]; Source
0x180010749  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001074e  lea     r14, [rdi+10h]
0x180010752  cmp     byte ptr [rdi+18h], 0
0x180010756  jnz     short loc_1800107D3
0x180010758  cmp     qword ptr [r14], 0
0x18001075c  jnz     short loc_18001079E
0x18001075e  call    cs:__imp_GetLastError
0x180010765  nop     dword ptr [rax+rax+00h]
0x18001076a  mov     ebx, eax
0x18001076c  xor     r8d, r8d; pcbe
0x18001076f  mov     rdx, rdi; pv
0x180010772  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180010779  call    cs:__imp_CreateThreadpoolTimer
0x180010780  nop     dword ptr [rax+rax+00h]
0x180010785  mov     rdx, rax
0x180010788  mov     rcx, r14
0x18001078b  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180010790  mov     ecx, ebx; dwErrCode
0x180010792  call    cs:__imp_SetLastError
0x180010799  nop     dword ptr [rax+rax+00h]
0x18001079e  mov     rcx, [r14]; pti
0x1800107a1  test    rcx, rcx
0x1800107a4  jz      short loc_1800107D3
0x1800107a6  mov     rax, 0FFFFFFFF4D2FA200h
0x1800107b0  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x1800107b5  mov     r9d, 124F8h; msWindowLength
0x1800107bb  xor     r8d, r8d; msPeriod
0x1800107be  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x1800107c3  call    cs:__imp_SetThreadpoolTimer
0x1800107ca  nop     dword ptr [rax+rax+00h]
0x1800107cf  mov     byte ptr [rdi+18h], 1
0x1800107d3  test    rsi, rsi
0x1800107d6  jz      short loc_1800107E8
0x1800107d8  mov     rcx, rsi; SRWLock
0x1800107db  call    cs:__imp_ReleaseSRWLockExclusive
0x1800107e2  nop     dword ptr [rax+rax+00h]
0x1800107e7  nop
0x1800107e8  mov     rbx, [rsp+48h+arg_8]
0x1800107ed  mov     rbp, [rsp+48h+arg_10]
0x1800107f2  add     rsp, 30h
0x1800107f6  pop     r14
0x1800107f8  pop     rdi
0x1800107f9  pop     rsi
0x1800107fa  retn
```
