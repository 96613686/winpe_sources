# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x14001c1c4`
- end: `0x14001c320`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `348`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x14001edd0`

## callees

- `0x14000942c`
- `0x14001c1c4`
- `0x140020274`
- `0x1400204b8`
- `0x140034010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001c2ff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001c2ff`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001c219`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001c219`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001c2bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001c2bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c288`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c288`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14001c2a3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14001c2a3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14001c2e7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14001c2e7`

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
0x14001c1c4  mov     [rsp+arg_8], rbx
0x14001c1c9  mov     [rsp+arg_10], rbp
0x14001c1ce  push    rsi
0x14001c1cf  push    rdi
0x14001c1d0  push    r14
0x14001c1d2  sub     rsp, 30h
0x14001c1d6  mov     ebx, r9d
0x14001c1d9  movzx   esi, r8w
0x14001c1dd  mov     r14d, edx
0x14001c1e0  mov     rdi, rcx
0x14001c1e3  cmp     byte ptr [rcx], 0
0x14001c1e6  jz      loc_14001C30C
0x14001c1ec  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14001c1f3  jnz     loc_14001C30C
0x14001c1f9  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14001c200  test    rax, rax
0x14001c203  jz      short loc_14001C212
0x14001c205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c20a  test    al, al
0x14001c20c  jnz     loc_14001C30C
0x14001c212  lea     rbp, [rdi+28h]
0x14001c216  mov     rcx, rbp; SRWLock
0x14001c219  call    cs:__imp_AcquireSRWLockExclusive
0x14001c220  nop     dword ptr [rax+rax+00h]
0x14001c225  xor     eax, eax
0x14001c227  mov     [rsp+48h+var_22], ax
0x14001c22c  mov     [rsp+48h+Source], r14d
0x14001c231  mov     [rsp+48h+var_24], si
0x14001c236  mov     [rsp+48h+var_20], ebx
0x14001c23a  lea     rbx, [rdi+0E8h]
0x14001c241  lea     esi, [rax+0Ch]
0x14001c244  mov     edx, esi; unsigned __int64
0x14001c246  mov     rcx, rbx; this
0x14001c249  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14001c24e  test    al, al
0x14001c250  jz      short loc_14001C278
0x14001c252  mov     rcx, [rbx+8]; Destination
0x14001c256  mov     rax, [rbx+10h]
0x14001c25a  sub     rax, rcx
0x14001c25d  cmp     rcx, [rbx+10h]
0x14001c261  sbb     rdx, rdx
0x14001c264  and     rdx, rax; DestinationSize
0x14001c267  mov     r9d, esi; SourceSize
0x14001c26a  lea     r8, [rsp+48h+Source]; Source
0x14001c26f  call    memcpy_s
0x14001c274  add     [rbx+8], rsi
0x14001c278  cmp     byte ptr [rdi+40h], 0
0x14001c27c  jnz     short loc_14001C2F7
0x14001c27e  lea     rsi, [rdi+38h]
0x14001c282  cmp     qword ptr [rsi], 0
0x14001c286  jnz     short loc_14001C2C8
0x14001c288  call    cs:__imp_GetLastError
0x14001c28f  nop     dword ptr [rax+rax+00h]
0x14001c294  mov     ebx, eax
0x14001c296  xor     r8d, r8d; pcbe
0x14001c299  mov     rdx, rdi; pv
0x14001c29c  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14001c2a3  call    cs:__imp_CreateThreadpoolTimer
0x14001c2aa  nop     dword ptr [rax+rax+00h]
0x14001c2af  mov     rdx, rax
0x14001c2b2  mov     rcx, rsi
0x14001c2b5  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x14001c2ba  mov     ecx, ebx; dwErrCode
0x14001c2bc  call    cs:__imp_SetLastError
0x14001c2c3  nop     dword ptr [rax+rax+00h]
0x14001c2c8  mov     rcx, [rsi]; pti
0x14001c2cb  test    rcx, rcx
0x14001c2ce  jz      short loc_14001C2F7
0x14001c2d0  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x14001c2d9  mov     r9d, 4E2h; msWindowLength
0x14001c2df  xor     r8d, r8d; msPeriod
0x14001c2e2  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x14001c2e7  call    cs:__imp_SetThreadpoolTimer
0x14001c2ee  nop     dword ptr [rax+rax+00h]
0x14001c2f3  mov     byte ptr [rdi+40h], 1
0x14001c2f7  test    rbp, rbp
0x14001c2fa  jz      short loc_14001C30C
0x14001c2fc  mov     rcx, rbp; SRWLock
0x14001c2ff  call    cs:__imp_ReleaseSRWLockExclusive
0x14001c306  nop     dword ptr [rax+rax+00h]
0x14001c30b  nop
0x14001c30c  mov     rbx, [rsp+48h+arg_8]
0x14001c311  mov     rbp, [rsp+48h+arg_10]
0x14001c316  add     rsp, 30h
0x14001c31a  pop     r14
0x14001c31c  pop     rdi
0x14001c31d  pop     rsi
0x14001c31e  retn
```
