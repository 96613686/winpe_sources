# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1800235e0`
- end: `0x180023725`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `325`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180025ef0`

## callees

- `0x1800235e0`
- `0x180026440`
- `0x1800265e4`
- `0x180031040`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800236fe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800236fe`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180023641`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180023641`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800236bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800236bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023687`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023687`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800236e6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800236e6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800236a2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800236a2`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        __int16 a3,
        int a4)
{
  struct _TP_TIMER **v8; // r14
  DWORD LastError; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _TP_TIMER *v11; // rcx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-58h] BYREF
  int Source; // [rsp+28h] [rbp-50h] BYREF
  __int16 v14; // [rsp+2Ch] [rbp-4Ch]
  __int16 v15; // [rsp+2Eh] [rbp-4Ah]
  int v16; // [rsp+30h] [rbp-48h]

  if ( LOBYTE(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 5);
    v15 = 0;
    Source = a2;
    v14 = a3;
    v16 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[29], &Source, 0xCu);
    v8 = (struct _TP_TIMER **)&pv[7];
    if ( !LOBYTE(pv[8].Ptr) )
    {
      if ( !*v8 )
      {
        LastError = GetLastError();
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          (struct _TP_TIMER **)&pv[7],
          ThreadpoolTimer);
        SetLastError(LastError);
      }
      v11 = *v8;
      if ( *v8 )
      {
        pftDueTime = (struct _FILETIME)-50000000LL;
        SetThreadpoolTimer(v11, &pftDueTime, 0, 0x4E2u);
        LOBYTE(pv[8].Ptr) = 1;
      }
    }
    if ( pv != (RTL_SRWLOCK *)-40LL )
      ReleaseSRWLockExclusive(pv + 5);
  }
}

```

## disassembly

```asm
0x1800235e0  push    rbx
0x1800235e2  push    rbp
0x1800235e3  push    rsi
0x1800235e4  push    rdi
0x1800235e5  push    r14
0x1800235e7  push    r15
0x1800235e9  sub     rsp, 48h
0x1800235ed  mov     rax, cs:__security_cookie
0x1800235f4  xor     rax, rsp
0x1800235f7  mov     [rsp+78h+var_40], rax
0x1800235fc  xor     r15d, r15d
0x1800235ff  mov     r14d, r9d
0x180023602  movzx   ebp, r8w
0x180023606  mov     ebx, edx
0x180023608  mov     rdi, rcx
0x18002360b  cmp     [rcx], r15b
0x18002360e  jz      loc_18002370A
0x180023614  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r15b; bool wil::details::g_processShutdownInProgress
0x18002361b  jnz     loc_18002370A
0x180023621  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180023628  test    rax, rax
0x18002362b  jz      short loc_18002363A
0x18002362d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023632  test    al, al
0x180023634  jnz     loc_18002370A
0x18002363a  lea     rsi, [rdi+28h]
0x18002363e  mov     rcx, rsi; SRWLock
0x180023641  call    cs:__imp_AcquireSRWLockExclusive
0x180023648  nop     dword ptr [rax+rax+00h]
0x18002364d  lea     rcx, [rdi+0E8h]; this
0x180023654  mov     [rsp+78h+var_4A], r15w
0x18002365a  mov     r8d, 0Ch; SourceSize
0x180023660  mov     [rsp+78h+Source], ebx
0x180023664  lea     rdx, [rsp+78h+Source]; Source
0x180023669  mov     [rsp+78h+var_4C], bp
0x18002366e  mov     [rsp+78h+var_48], r14d
0x180023673  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180023678  lea     r14, [rdi+38h]
0x18002367c  cmp     [rdi+40h], r15b
0x180023680  jnz     short loc_1800236F6
0x180023682  cmp     [r14], r15
0x180023685  jnz     short loc_1800236C7
0x180023687  call    cs:__imp_GetLastError
0x18002368e  nop     dword ptr [rax+rax+00h]
0x180023693  xor     r8d, r8d; pcbe
0x180023696  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18002369d  mov     rdx, rdi; pv
0x1800236a0  mov     ebx, eax
0x1800236a2  call    cs:__imp_CreateThreadpoolTimer
0x1800236a9  nop     dword ptr [rax+rax+00h]
0x1800236ae  mov     rdx, rax
0x1800236b1  mov     rcx, r14
0x1800236b4  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800236b9  mov     ecx, ebx; dwErrCode
0x1800236bb  call    cs:__imp_SetLastError
0x1800236c2  nop     dword ptr [rax+rax+00h]
0x1800236c7  mov     rcx, [r14]; pti
0x1800236ca  test    rcx, rcx
0x1800236cd  jz      short loc_1800236F6
0x1800236cf  mov     r9d, 4E2h; msWindowLength
0x1800236d5  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x1800236de  xor     r8d, r8d; msPeriod
0x1800236e1  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x1800236e6  call    cs:__imp_SetThreadpoolTimer
0x1800236ed  nop     dword ptr [rax+rax+00h]
0x1800236f2  mov     byte ptr [rdi+40h], 1
0x1800236f6  test    rsi, rsi
0x1800236f9  jz      short loc_18002370A
0x1800236fb  mov     rcx, rsi; SRWLock
0x1800236fe  call    cs:__imp_ReleaseSRWLockExclusive
0x180023705  nop     dword ptr [rax+rax+00h]
0x18002370a  mov     rcx, [rsp+78h+var_40]
0x18002370f  xor     rcx, rsp; StackCookie
0x180023712  call    __security_check_cookie
0x180023717  add     rsp, 48h
0x18002371b  pop     r15
0x18002371d  pop     r14
0x18002371f  pop     rdi
0x180023720  pop     rsi
0x180023721  pop     rbp
0x180023722  pop     rbx
0x180023723  retn
```
