# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1800068d8`
- end: `0x180006a1a`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `322`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800094a0`

## callees

- `0x1800068d8`
- `0x180009abc`
- `0x180009c50`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800069f3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800069f3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006936`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006936`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000697c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000697c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800069b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800069b0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180006997`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180006997`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800069db`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800069db`

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
0x1800068d8  mov     [rsp+arg_8], rbx
0x1800068dd  mov     [rsp+arg_10], rbp
0x1800068e2  mov     [rsp+arg_18], rsi
0x1800068e7  push    rdi
0x1800068e8  push    r14
0x1800068ea  push    r15
0x1800068ec  sub     rsp, 30h
0x1800068f0  mov     ebx, r9d
0x1800068f3  movzx   ebp, r8w
0x1800068f7  mov     r14d, edx
0x1800068fa  mov     rdi, rcx
0x1800068fd  xor     r15d, r15d
0x180006900  cmp     [rcx], r15b
0x180006903  jz      loc_180006A00
0x180006909  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r15b; bool wil::details::g_processShutdownInProgress
0x180006910  jnz     loc_180006A00
0x180006916  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000691d  test    rax, rax
0x180006920  jz      short loc_18000692F
0x180006922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006927  test    al, al
0x180006929  jnz     loc_180006A00
0x18000692f  lea     rsi, [rdi+28h]
0x180006933  mov     rcx, rsi; SRWLock
0x180006936  call    cs:__imp_AcquireSRWLockExclusive
0x18000693d  nop     dword ptr [rax+rax+00h]
0x180006942  mov     [rsp+48h+var_22], r15w
0x180006948  mov     [rsp+48h+Source], r14d
0x18000694d  mov     [rsp+48h+var_24], bp
0x180006952  mov     [rsp+48h+var_20], ebx
0x180006956  lea     rcx, [rdi+0E8h]; this
0x18000695d  mov     r8d, 0Ch; SourceSize
0x180006963  lea     rdx, [rsp+48h+Source]; Source
0x180006968  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000696d  lea     r14, [rdi+38h]
0x180006971  cmp     [rdi+40h], r15b
0x180006975  jnz     short loc_1800069EB
0x180006977  cmp     [r14], r15
0x18000697a  jnz     short loc_1800069BC
0x18000697c  call    cs:__imp_GetLastError
0x180006983  nop     dword ptr [rax+rax+00h]
0x180006988  mov     ebx, eax
0x18000698a  xor     r8d, r8d; pcbe
0x18000698d  mov     rdx, rdi; pv
0x180006990  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180006997  call    cs:__imp_CreateThreadpoolTimer
0x18000699e  nop     dword ptr [rax+rax+00h]
0x1800069a3  mov     rdx, rax
0x1800069a6  mov     rcx, r14
0x1800069a9  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800069ae  mov     ecx, ebx; dwErrCode
0x1800069b0  call    cs:__imp_SetLastError
0x1800069b7  nop     dword ptr [rax+rax+00h]
0x1800069bc  mov     rcx, [r14]; pti
0x1800069bf  test    rcx, rcx
0x1800069c2  jz      short loc_1800069EB
0x1800069c4  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x1800069cd  mov     r9d, 4E2h; msWindowLength
0x1800069d3  xor     r8d, r8d; msPeriod
0x1800069d6  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x1800069db  call    cs:__imp_SetThreadpoolTimer
0x1800069e2  nop     dword ptr [rax+rax+00h]
0x1800069e7  mov     byte ptr [rdi+40h], 1
0x1800069eb  test    rsi, rsi
0x1800069ee  jz      short loc_180006A00
0x1800069f0  mov     rcx, rsi; SRWLock
0x1800069f3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800069fa  nop     dword ptr [rax+rax+00h]
0x1800069ff  nop
0x180006a00  mov     rbx, [rsp+48h+arg_8]
0x180006a05  mov     rbp, [rsp+48h+arg_10]
0x180006a0a  mov     rsi, [rsp+48h+arg_18]
0x180006a0f  add     rsp, 30h
0x180006a13  pop     r15
0x180006a15  pop     r14
0x180006a17  pop     rdi
0x180006a18  retn
```
