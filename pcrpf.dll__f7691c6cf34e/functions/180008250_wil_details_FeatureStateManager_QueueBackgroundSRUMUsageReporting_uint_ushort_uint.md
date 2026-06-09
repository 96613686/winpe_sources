# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180008250`
- end: `0x1800083ac`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `348`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18000b050`

## callees

- `0x180008250`
- `0x18000b7a8`
- `0x18000b8a0`
- `0x18000bd1c`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800082a5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800082a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000838b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000838b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008348`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008348`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008314`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008314`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000832f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000832f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008373`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008373`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        __int16 a3,
        int a4)
{
  struct _TP_TIMER **v8; // rsi
  DWORD LastError; // ebx
  PTP_TIMER ThreadpoolTimer; // rax
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
    if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[29], 0xCu) )
    {
      memcpy_s(
        pv[30].Ptr,
        ((char *)pv[31].Ptr - (char *)pv[30].Ptr) & -(__int64)(pv[30].Ptr < pv[31].Ptr),
        &Source,
        0xCu);
      pv[30].Ptr = (char *)pv[30].Ptr + 12;
    }
    if ( !LOBYTE(pv[8].Ptr) )
    {
      v8 = (struct _TP_TIMER **)&pv[7];
      if ( !pv[7].Ptr )
      {
        LastError = GetLastError();
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          &pv[7],
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
0x180008250  mov     [rsp+arg_8], rbx
0x180008255  mov     [rsp+arg_10], rbp
0x18000825a  push    rsi
0x18000825b  push    rdi
0x18000825c  push    r14
0x18000825e  sub     rsp, 30h
0x180008262  mov     ebx, r9d
0x180008265  movzx   esi, r8w
0x180008269  mov     r14d, edx
0x18000826c  mov     rdi, rcx
0x18000826f  cmp     byte ptr [rcx], 0
0x180008272  jz      loc_180008398
0x180008278  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000827f  jnz     loc_180008398
0x180008285  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000828c  test    rax, rax
0x18000828f  jz      short loc_18000829E
0x180008291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008296  test    al, al
0x180008298  jnz     loc_180008398
0x18000829e  lea     rbp, [rdi+28h]
0x1800082a2  mov     rcx, rbp; SRWLock
0x1800082a5  call    cs:__imp_AcquireSRWLockExclusive
0x1800082ac  nop     dword ptr [rax+rax+00h]
0x1800082b1  xor     eax, eax
0x1800082b3  mov     [rsp+48h+var_22], ax
0x1800082b8  mov     [rsp+48h+Source], r14d
0x1800082bd  mov     [rsp+48h+var_24], si
0x1800082c2  mov     [rsp+48h+var_20], ebx
0x1800082c6  lea     rbx, [rdi+0E8h]
0x1800082cd  lea     esi, [rax+0Ch]
0x1800082d0  mov     edx, esi; unsigned __int64
0x1800082d2  mov     rcx, rbx; this
0x1800082d5  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800082da  test    al, al
0x1800082dc  jz      short loc_180008304
0x1800082de  mov     rcx, [rbx+8]; Destination
0x1800082e2  mov     rax, [rbx+10h]
0x1800082e6  sub     rax, rcx
0x1800082e9  cmp     rcx, [rbx+10h]
0x1800082ed  sbb     rdx, rdx
0x1800082f0  and     rdx, rax; DestinationSize
0x1800082f3  mov     r9d, esi; SourceSize
0x1800082f6  lea     r8, [rsp+48h+Source]; Source
0x1800082fb  call    memcpy_s
0x180008300  add     [rbx+8], rsi
0x180008304  cmp     byte ptr [rdi+40h], 0
0x180008308  jnz     short loc_180008383
0x18000830a  lea     rsi, [rdi+38h]
0x18000830e  cmp     qword ptr [rsi], 0
0x180008312  jnz     short loc_180008354
0x180008314  call    cs:__imp_GetLastError
0x18000831b  nop     dword ptr [rax+rax+00h]
0x180008320  mov     ebx, eax
0x180008322  xor     r8d, r8d; pcbe
0x180008325  mov     rdx, rdi; pv
0x180008328  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000832f  call    cs:__imp_CreateThreadpoolTimer
0x180008336  nop     dword ptr [rax+rax+00h]
0x18000833b  mov     rdx, rax
0x18000833e  mov     rcx, rsi
0x180008341  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180008346  mov     ecx, ebx; dwErrCode
0x180008348  call    cs:__imp_SetLastError
0x18000834f  nop     dword ptr [rax+rax+00h]
0x180008354  mov     rcx, [rsi]; pti
0x180008357  test    rcx, rcx
0x18000835a  jz      short loc_180008383
0x18000835c  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180008365  mov     r9d, 4E2h; msWindowLength
0x18000836b  xor     r8d, r8d; msPeriod
0x18000836e  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x180008373  call    cs:__imp_SetThreadpoolTimer
0x18000837a  nop     dword ptr [rax+rax+00h]
0x18000837f  mov     byte ptr [rdi+40h], 1
0x180008383  test    rbp, rbp
0x180008386  jz      short loc_180008398
0x180008388  mov     rcx, rbp; SRWLock
0x18000838b  call    cs:__imp_ReleaseSRWLockExclusive
0x180008392  nop     dword ptr [rax+rax+00h]
0x180008397  nop
0x180008398  mov     rbx, [rsp+48h+arg_8]
0x18000839d  mov     rbp, [rsp+48h+arg_10]
0x1800083a2  add     rsp, 30h
0x1800083a6  pop     r14
0x1800083a8  pop     rdi
0x1800083a9  pop     rsi
0x1800083aa  retn
```
