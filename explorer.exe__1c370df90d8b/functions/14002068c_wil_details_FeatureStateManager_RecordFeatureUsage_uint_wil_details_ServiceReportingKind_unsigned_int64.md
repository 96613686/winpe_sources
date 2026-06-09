# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x14002068c`
- end: `0x140020824`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `408`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x14008d950`

## callees

- `0x14002036c`
- `0x14002068c`
- `0x14002082c`
- `0x1400208a8`
- `0x140021804`
- `0x140108f30`
- `0x1401db010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140020710`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002078e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140020710`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002078e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400206da`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14002073a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400206da`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14002073a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140020778`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140020778`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020750`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020750`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140020765`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140020765`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400207bf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400207bf`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4)
{
  __int64 v8; // rsi
  int v9; // eax
  char v10; // bl
  struct _TP_TIMER **v11; // r14
  DWORD LastError; // ebx
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v14; // rcx
  struct _FILETIME pftDueTime; // [rsp+60h] [rbp+8h] BYREF

  if ( !*(_BYTE *)a1 || !wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1) )
    return;
  v8 = *(_QWORD *)(a1 + 24);
  if ( a3 == 254 )
  {
    wil::details_abi::FeatureStateData::RecordUsage(*(PSRWLOCK *)(a1 + 24));
LABEL_11:
    if ( !wil::details::g_processShutdownInProgress
      && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
    {
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 32));
      if ( !*(_BYTE *)(a1 + 65) )
      {
        v11 = (struct _TP_TIMER **)(a1 + 48);
        if ( !*(_QWORD *)(a1 + 48) )
        {
          LastError = GetLastError();
          ThreadpoolTimer = CreateThreadpoolTimer(
                              _lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_,
                              (PVOID)a1,
                              0);
          wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
            a1 + 48,
            ThreadpoolTimer);
          SetLastError(LastError);
        }
        v14 = *v11;
        if ( *v11 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v14, &pftDueTime, 0, 0x124F8u);
          *(_BYTE *)(a1 + 65) = 1;
        }
      }
      if ( a1 != -32 )
        ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 32));
    }
    return;
  }
  if ( a3 < 0xC8 || (int)a3 >= 256 && a3 < 0x200 )
  {
    AcquireSRWLockExclusive(*(PSRWLOCK *)(a1 + 24));
    if ( a3 <= 7 && (v9 = 204, _bittest(&v9, a3)) || a3 - 256 <= 0x7F )
    {
      wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,0>::RecordUsage((wil::details_abi::RawUsageIndex *)(v8 + 8));
      v10 = *(_BYTE *)(v8 + 64);
    }
    else
    {
      v10 = wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,2>::RecordUsage(
              v8 + 72,
              a3,
              a2,
              a4);
    }
    if ( v8 )
      ReleaseSRWLockExclusive((PSRWLOCK)v8);
    if ( v10 )
      goto LABEL_11;
  }
}

```

## disassembly

```asm
0x14002068c  push    rbx
0x14002068e  push    rbp
0x14002068f  push    rsi
0x140020690  push    rdi
0x140020691  push    r14
0x140020693  push    r15
0x140020695  sub     rsp, 28h
0x140020699  mov     r15, r9
0x14002069c  mov     ebx, r8d
0x14002069f  mov     r14d, edx
0x1400206a2  mov     rdi, rcx
0x1400206a5  cmp     byte ptr [rcx], 0
0x1400206a8  jz      loc_140020795
0x1400206ae  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1400206b3  test    al, al
0x1400206b5  jz      loc_140020795
0x1400206bb  mov     rsi, [rdi+18h]
0x1400206bf  cmp     ebx, 0FEh
0x1400206c5  jz      loc_1400207F0
0x1400206cb  cmp     ebx, 0C8h
0x1400206d1  jnb     loc_1400207DA
0x1400206d7  mov     rcx, rsi; SRWLock
0x1400206da  call    cs:__imp_AcquireSRWLockExclusive
0x1400206e0  cmp     ebx, 7
0x1400206e3  ja      loc_1400207FD
0x1400206e9  mov     eax, 0CCh
0x1400206ee  bt      eax, ebx
0x1400206f1  jnb     loc_1400207FD
0x1400206f7  mov     r8d, r14d
0x1400206fa  mov     edx, ebx
0x1400206fc  lea     rcx, [rsi+8]; this
0x140020700  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x140020705  mov     bl, [rsi+40h]
0x140020708  test    rsi, rsi
0x14002070b  jz      short loc_140020716
0x14002070d  mov     rcx, rsi; SRWLock
0x140020710  call    cs:__imp_ReleaseSRWLockExclusive
0x140020716  test    bl, bl
0x140020718  jz      short loc_140020795
0x14002071a  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140020721  jnz     short loc_140020795
0x140020723  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14002072a  test    rax, rax
0x14002072d  jnz     loc_1400207CB
0x140020733  lea     rsi, [rdi+20h]
0x140020737  mov     rcx, rsi; SRWLock
0x14002073a  call    cs:__imp_AcquireSRWLockExclusive
0x140020740  cmp     byte ptr [rdi+41h], 0
0x140020744  jnz     short loc_140020786
0x140020746  lea     r14, [rdi+30h]
0x14002074a  cmp     qword ptr [r14], 0
0x14002074e  jnz     short loc_14002077E
0x140020750  call    cs:__imp_GetLastError
0x140020756  mov     ebx, eax
0x140020758  xor     r8d, r8d; pcbe
0x14002075b  mov     rdx, rdi; pv
0x14002075e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140020765  call    cs:__imp_CreateThreadpoolTimer
0x14002076b  mov     rdx, rax
0x14002076e  mov     rcx, r14
0x140020771  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x140020776  mov     ecx, ebx; dwErrCode
0x140020778  call    cs:__imp_SetLastError
0x14002077e  mov     rcx, [r14]; pti
0x140020781  test    rcx, rcx
0x140020784  jnz     short loc_1400207A2
0x140020786  test    rsi, rsi
0x140020789  jz      short loc_140020795
0x14002078b  mov     rcx, rsi; SRWLock
0x14002078e  call    cs:__imp_ReleaseSRWLockExclusive
0x140020794  nop
0x140020795  add     rsp, 28h
0x140020799  pop     r15
0x14002079b  pop     r14
0x14002079d  pop     rdi
0x14002079e  pop     rsi
0x14002079f  pop     rbp
0x1400207a0  pop     rbx
0x1400207a1  retn
0x1400207a2  mov     rax, 0FFFFFFFF4D2FA200h
0x1400207ac  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x1400207b1  mov     r9d, 124F8h; msWindowLength
0x1400207b7  xor     r8d, r8d; msPeriod
0x1400207ba  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x1400207bf  call    cs:__imp_SetThreadpoolTimer
0x1400207c5  mov     byte ptr [rdi+41h], 1
0x1400207c9  jmp     short loc_140020786
0x1400207cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400207d0  test    al, al
0x1400207d2  jz      loc_140020733
0x1400207d8  jmp     short loc_140020795
0x1400207da  cmp     ebx, 100h
0x1400207e0  jl      short loc_140020795
0x1400207e2  cmp     ebx, 200h
0x1400207e8  jb      loc_1400206D7
0x1400207ee  jmp     short loc_140020795
0x1400207f0  mov     rcx, rsi; SRWLock
0x1400207f3  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1400207f8  jmp     loc_14002071A
0x1400207fd  lea     eax, [rbx-100h]
0x140020803  cmp     eax, 7Fh
0x140020806  jbe     loc_1400206F7
0x14002080c  mov     r9d, r15d
0x14002080f  lea     rcx, [rsi+48h]
0x140020813  mov     r8d, r14d
0x140020816  mov     edx, ebx
0x140020818  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x14002081d  mov     bl, al
0x14002081f  jmp     loc_140020708
```
