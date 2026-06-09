# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1800265d0`
- end: `0x180026778`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `424`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180028b30`

## callees

- `0x18001e1d0`
- `0x1800238e0`
- `0x1800265d0`
- `0x180026800`
- `0x180026860`
- `0x1800268c0`
- `0x180029820`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180026644`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800266d9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180026644`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800266d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180026694`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180026753`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180026694`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180026753`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026715`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026715`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800266ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800266ec`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180026701`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180026701`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180026741`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180026741`

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
  DWORD LastError; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _TP_TIMER *v13; // rcx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-38h] BYREF

  if ( !*(_BYTE *)a1 || !wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1) )
    return;
  v8 = *(_QWORD *)(a1 + 24);
  if ( a3 == 254 )
  {
    wil::details_abi::FeatureStateData::RecordUsage(*(PSRWLOCK *)(a1 + 24));
LABEL_17:
    if ( !wil::details::g_processShutdownInProgress
      && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
    {
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 32));
      if ( !*(_BYTE *)(a1 + 65) )
      {
        if ( !*(_QWORD *)(a1 + 48) )
        {
          LastError = GetLastError();
          ThreadpoolTimer = CreateThreadpoolTimer(
                              _lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_,
                              (PVOID)a1,
                              0);
          wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
            (struct _TP_TIMER **)(a1 + 48),
            ThreadpoolTimer);
          SetLastError(LastError);
        }
        v13 = *(struct _TP_TIMER **)(a1 + 48);
        if ( v13 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v13, &pftDueTime, 0, 0x124F8u);
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
      wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,0>::RecordUsage(v8 + 8, a3, a2);
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
      goto LABEL_17;
  }
}

```

## disassembly

```asm
0x1800265d0  mov     [rsp+arg_18], rbx
0x1800265d5  push    rbp
0x1800265d6  push    rsi
0x1800265d7  push    rdi
0x1800265d8  push    r14
0x1800265da  push    r15
0x1800265dc  sub     rsp, 30h
0x1800265e0  mov     rax, cs:__security_cookie
0x1800265e7  xor     rax, rsp
0x1800265ea  mov     [rsp+58h+var_30], rax
0x1800265ef  mov     r15, r9
0x1800265f2  mov     ebx, r8d
0x1800265f5  mov     r14d, edx
0x1800265f8  mov     rdi, rcx
0x1800265fb  cmp     byte ptr [rcx], 0
0x1800265fe  jz      loc_18002675A
0x180026604  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180026609  test    al, al
0x18002660b  jz      loc_18002675A
0x180026611  mov     rsi, [rdi+18h]
0x180026615  cmp     ebx, 0FEh
0x18002661b  jz      loc_1800266A4
0x180026621  cmp     ebx, 0C8h
0x180026627  jb      short loc_180026641
0x180026629  cmp     ebx, 100h
0x18002662f  jl      loc_18002675A
0x180026635  cmp     ebx, 200h
0x18002663b  jnb     loc_18002675A
0x180026641  mov     rcx, rsi; SRWLock
0x180026644  call    cs:__imp_AcquireSRWLockExclusive
0x18002664a  cmp     ebx, 7
0x18002664d  ja      short loc_180026659
0x18002664f  mov     eax, 0CCh
0x180026654  bt      eax, ebx
0x180026657  jb      short loc_18002667A
0x180026659  lea     eax, [rbx-100h]
0x18002665f  cmp     eax, 7Fh
0x180026662  jbe     short loc_18002667A
0x180026664  mov     r9d, r15d
0x180026667  lea     rcx, [rsi+48h]
0x18002666b  mov     r8d, r14d
0x18002666e  mov     edx, ebx
0x180026670  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180026675  movzx   ebx, al
0x180026678  jmp     short loc_18002668C
0x18002667a  mov     r8d, r14d
0x18002667d  mov     edx, ebx
0x18002667f  lea     rcx, [rsi+8]
0x180026683  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180026688  movzx   ebx, byte ptr [rsi+40h]
0x18002668c  test    rsi, rsi
0x18002668f  jz      short loc_18002669A
0x180026691  mov     rcx, rsi; SRWLock
0x180026694  call    cs:__imp_ReleaseSRWLockExclusive
0x18002669a  test    bl, bl
0x18002669c  jz      loc_18002675A
0x1800266a2  jmp     short loc_1800266AC
0x1800266a4  mov     rcx, rsi; SRWLock
0x1800266a7  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800266ac  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800266b3  jnz     loc_18002675A
0x1800266b9  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800266c0  test    rax, rax
0x1800266c3  jz      short loc_1800266D2
0x1800266c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800266ca  test    al, al
0x1800266cc  jnz     loc_18002675A
0x1800266d2  lea     rsi, [rdi+20h]
0x1800266d6  mov     rcx, rsi; SRWLock
0x1800266d9  call    cs:__imp_AcquireSRWLockExclusive
0x1800266df  cmp     byte ptr [rdi+41h], 0
0x1800266e3  jnz     short loc_18002674B
0x1800266e5  cmp     qword ptr [rdi+30h], 0
0x1800266ea  jnz     short loc_18002671B
0x1800266ec  call    cs:__imp_GetLastError
0x1800266f2  mov     ebx, eax
0x1800266f4  xor     r8d, r8d; pcbe
0x1800266f7  mov     rdx, rdi; pv
0x1800266fa  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180026701  call    cs:__imp_CreateThreadpoolTimer
0x180026707  mov     rdx, rax
0x18002670a  lea     rcx, [rdi+30h]
0x18002670e  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180026713  mov     ecx, ebx; dwErrCode
0x180026715  call    cs:__imp_SetLastError
0x18002671b  mov     rcx, [rdi+30h]; pti
0x18002671f  test    rcx, rcx
0x180026722  jz      short loc_18002674B
0x180026724  mov     rax, 0FFFFFFFF4D2FA200h
0x18002672e  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x180026733  mov     r9d, 124F8h; msWindowLength
0x180026739  xor     r8d, r8d; msPeriod
0x18002673c  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x180026741  call    cs:__imp_SetThreadpoolTimer
0x180026747  mov     byte ptr [rdi+41h], 1
0x18002674b  test    rsi, rsi
0x18002674e  jz      short loc_18002675A
0x180026750  mov     rcx, rsi; SRWLock
0x180026753  call    cs:__imp_ReleaseSRWLockExclusive
0x180026759  nop
0x18002675a  mov     rcx, [rsp+58h+var_30]
0x18002675f  xor     rcx, rsp; StackCookie
0x180026762  call    __security_check_cookie
0x180026767  mov     rbx, [rsp+58h+arg_18]
0x18002676c  add     rsp, 30h
0x180026770  pop     r15
0x180026772  pop     r14
0x180026774  pop     rdi
0x180026775  pop     rsi
0x180026776  pop     rbp
0x180026777  retn
```
