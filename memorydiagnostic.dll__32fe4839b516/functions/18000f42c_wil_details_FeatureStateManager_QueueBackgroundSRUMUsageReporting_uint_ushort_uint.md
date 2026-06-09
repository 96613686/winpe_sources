# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000f42c`
- end: `0x18000f56e`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `322`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180015940`

## callees

- `0x18000f42c`
- `0x1800183b4`
- `0x180018824`
- `0x180024010`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x18000f4eb`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000f4eb`
- `KERNEL32!SetThreadpoolTimer` at `0x18000f52f`
- `KERNEL32!SetThreadpoolTimer` at `0x18000f52f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000f48a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000f48a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000f547`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000f547`
- `KERNEL32!GetLastError` at `0x18000f4d0`
- `KERNEL32!GetLastError` at `0x18000f4d0`
- `KERNEL32!SetLastError` at `0x18000f504`
- `KERNEL32!SetLastError` at `0x18000f504`

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
  int Source; // [rsp+20h] [rbp-28h] BYREF
  __int16 v13; // [rsp+24h] [rbp-24h]
  __int16 v14; // [rsp+26h] [rbp-22h]
  int v15; // [rsp+28h] [rbp-20h]
  struct _FILETIME pftDueTime; // [rsp+50h] [rbp+8h] BYREF

  if ( LOBYTE(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 5);
    v14 = 0;
    Source = a2;
    v13 = a3;
    v15 = a4;
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
0x18000f42c  mov     [rsp+arg_8], rbx
0x18000f431  mov     [rsp+arg_10], rbp
0x18000f436  mov     [rsp+arg_18], rsi
0x18000f43b  push    rdi
0x18000f43c  push    r14
0x18000f43e  push    r15
0x18000f440  sub     rsp, 30h
0x18000f444  mov     ebx, r9d
0x18000f447  movzx   ebp, r8w
0x18000f44b  mov     r14d, edx
0x18000f44e  mov     rdi, rcx
0x18000f451  xor     r15d, r15d
0x18000f454  cmp     [rcx], r15b
0x18000f457  jz      loc_18000F554
0x18000f45d  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r15b; bool wil::details::g_processShutdownInProgress
0x18000f464  jnz     loc_18000F554
0x18000f46a  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000f471  test    rax, rax
0x18000f474  jz      short loc_18000F483
0x18000f476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f47b  test    al, al
0x18000f47d  jnz     loc_18000F554
0x18000f483  lea     rsi, [rdi+28h]
0x18000f487  mov     rcx, rsi; SRWLock
0x18000f48a  call    cs:__imp_AcquireSRWLockExclusive
0x18000f491  nop     dword ptr [rax+rax+00h]
0x18000f496  mov     [rsp+48h+var_22], r15w
0x18000f49c  mov     [rsp+48h+Source], r14d
0x18000f4a1  mov     [rsp+48h+var_24], bp
0x18000f4a6  mov     [rsp+48h+var_20], ebx
0x18000f4aa  lea     rcx, [rdi+0E8h]; this
0x18000f4b1  mov     r8d, 0Ch; SourceSize
0x18000f4b7  lea     rdx, [rsp+48h+Source]; Source
0x18000f4bc  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000f4c1  lea     r14, [rdi+38h]
0x18000f4c5  cmp     [rdi+40h], r15b
0x18000f4c9  jnz     short loc_18000F53F
0x18000f4cb  cmp     [r14], r15
0x18000f4ce  jnz     short loc_18000F510
0x18000f4d0  call    cs:__imp_GetLastError
0x18000f4d7  nop     dword ptr [rax+rax+00h]
0x18000f4dc  mov     ebx, eax
0x18000f4de  xor     r8d, r8d; pcbe
0x18000f4e1  mov     rdx, rdi; pv
0x18000f4e4  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000f4eb  call    cs:__imp_CreateThreadpoolTimer
0x18000f4f2  nop     dword ptr [rax+rax+00h]
0x18000f4f7  mov     rdx, rax
0x18000f4fa  mov     rcx, r14
0x18000f4fd  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000f502  mov     ecx, ebx; dwErrCode
0x18000f504  call    cs:__imp_SetLastError
0x18000f50b  nop     dword ptr [rax+rax+00h]
0x18000f510  mov     rcx, [r14]; pti
0x18000f513  test    rcx, rcx
0x18000f516  jz      short loc_18000F53F
0x18000f518  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000f521  mov     r9d, 4E2h; msWindowLength
0x18000f527  xor     r8d, r8d; msPeriod
0x18000f52a  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x18000f52f  call    cs:__imp_SetThreadpoolTimer
0x18000f536  nop     dword ptr [rax+rax+00h]
0x18000f53b  mov     byte ptr [rdi+40h], 1
0x18000f53f  test    rsi, rsi
0x18000f542  jz      short loc_18000F554
0x18000f544  mov     rcx, rsi; SRWLock
0x18000f547  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f54e  nop     dword ptr [rax+rax+00h]
0x18000f553  nop
0x18000f554  mov     rbx, [rsp+48h+arg_8]
0x18000f559  mov     rbp, [rsp+48h+arg_10]
0x18000f55e  mov     rsi, [rsp+48h+arg_18]
0x18000f563  add     rsp, 30h
0x18000f567  pop     r15
0x18000f569  pop     r14
0x18000f56b  pop     rdi
0x18000f56c  retn
```
