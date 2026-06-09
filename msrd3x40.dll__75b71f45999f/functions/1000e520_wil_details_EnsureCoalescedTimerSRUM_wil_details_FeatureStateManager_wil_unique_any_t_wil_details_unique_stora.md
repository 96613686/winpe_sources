# wil::details::EnsureCoalescedTimerSRUM<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<uint,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)

- ea: `0x1000e520`
- end: `0x1000e5e2`
- name: `??$EnsureCoalescedTimerSRUM@VFeatureStateManager@details@wil@@@details@wil@@YGXAAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PAU_TP_TIMER@@P6GXPAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SGX0@ZU?$integral_constant@I$0A@@wistd@@PAU1@PAU1@$0A@$$T@details@wil@@@details@wil@@@1@AA_NPAVFeatureStateManager@01@@Z`
- size: `194`
- prototype: `int __stdcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1000cd70`

## callees

- `0x1000e520`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1000e597`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1000e5a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1000e597`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1000e5a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1000e540`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1000e568`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1000e540`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1000e568`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1000e57a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1000e5d0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1000e57a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1000e5d0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1000e590`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1000e590`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1000e586`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1000e586`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1000e554`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1000e554`

## pseudocode

```c
void __fastcall wil::details::EnsureCoalescedTimerSRUM<wil::details::FeatureStateManager>(
        struct _TP_TIMER **a1,
        _BYTE *a2,
        PVOID pv)
{
  DWORD LastError; // esi
  struct _TP_TIMER *v6; // eax
  DWORD dwLowDateTime; // [esp-4h] [ebp-24h]
  struct _TP_TIMER *pti; // [esp+10h] [ebp-10h]
  PTP_TIMER ThreadpoolTimer; // [esp+14h] [ebp-Ch]
  struct _FILETIME dwErrCode; // [esp+18h] [ebp-8h] BYREF

  if ( !*a2 )
  {
    if ( !*a1 )
    {
      dwErrCode.dwLowDateTime = GetLastError();
      ThreadpoolTimer = CreateThreadpoolTimer(
                          _lambda_258f5224b53a55ce40a9b756bd0c10b5_::_lambda_invoker_stdcall_,
                          pv,
                          0);
      pti = *a1;
      if ( *a1 )
      {
        LastError = GetLastError();
        SetThreadpoolTimer(pti, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(pti, 1);
        CloseThreadpoolTimer(pti);
        SetLastError(LastError);
      }
      dwLowDateTime = dwErrCode.dwLowDateTime;
      *a1 = ThreadpoolTimer;
      SetLastError(dwLowDateTime);
    }
    v6 = *a1;
    if ( *a1 )
    {
      dwErrCode.dwLowDateTime = -50000000;
      dwErrCode.dwHighDateTime = -1;
      SetThreadpoolTimer(v6, &dwErrCode, 0, 0x4E2u);
      *a2 = 1;
    }
  }
}

```

## disassembly

```asm
0x1000e520  mov     edi, edi
0x1000e522  push    ebp
0x1000e523  mov     ebp, esp
0x1000e525  and     esp, 0FFFFFFF8h
0x1000e528  sub     esp, 14h
0x1000e52b  push    ebx
0x1000e52c  mov     ebx, edx
0x1000e52e  push    esi
0x1000e52f  push    edi
0x1000e530  mov     edi, ecx
0x1000e532  cmp     byte ptr [ebx], 0
0x1000e535  jnz     loc_1000E5D9
0x1000e53b  cmp     dword ptr [edi], 0
0x1000e53e  jnz     short loc_1000E5AD
0x1000e540  call    ds:__imp__GetLastError@0; GetLastError()
0x1000e546  push    0; pcbe
0x1000e548  push    [ebp+pv]; pv
0x1000e54b  mov     [esp+28h+dwErrCode], eax
0x1000e54f  push    offset ?_lambda_invoker_stdcall_@_lambda_258f5224b53a55ce40a9b756bd0c10b5_@@CG@PAU_TP_CALLBACK_INSTANCE@@PAXPAU_TP_TIMER@@@Z; pfnti
0x1000e554  call    ds:__imp__CreateThreadpoolTimer@12; CreateThreadpoolTimer(x,x,x)
0x1000e55a  mov     [esp+20h+var_C], eax
0x1000e55e  mov     eax, [edi]
0x1000e560  mov     [esp+20h+pti], eax
0x1000e564  test    eax, eax
0x1000e566  jz      short loc_1000E59D
0x1000e568  call    ds:__imp__GetLastError@0; GetLastError()
0x1000e56e  push    0; msWindowLength
0x1000e570  push    0; msPeriod
0x1000e572  push    0; pftDueTime
0x1000e574  push    [esp+2Ch+pti]; pti
0x1000e578  mov     esi, eax
0x1000e57a  call    ds:__imp__SetThreadpoolTimer@16; SetThreadpoolTimer(x,x,x,x)
0x1000e580  push    1; fCancelPendingCallbacks
0x1000e582  push    [esp+24h+pti]; pti
0x1000e586  call    ds:__imp__WaitForThreadpoolTimerCallbacks@8; WaitForThreadpoolTimerCallbacks(x,x)
0x1000e58c  push    [esp+20h+pti]; pti
0x1000e590  call    ds:__imp__CloseThreadpoolTimer@4; CloseThreadpoolTimer(x)
0x1000e596  push    esi; dwErrCode
0x1000e597  call    ds:__imp__SetLastError@4; SetLastError(x)
0x1000e59d  mov     eax, [esp+20h+var_C]
0x1000e5a1  push    [esp+20h+dwErrCode]; dwErrCode
0x1000e5a5  mov     [edi], eax
0x1000e5a7  call    ds:__imp__SetLastError@4; SetLastError(x)
0x1000e5ad  mov     eax, [edi]
0x1000e5af  test    eax, eax
0x1000e5b1  jz      short loc_1000E5D9
0x1000e5b3  push    4E2h; msWindowLength
0x1000e5b8  push    0; msPeriod
0x1000e5ba  lea     ecx, [esp+28h+dwErrCode]
0x1000e5be  mov     [esp+28h+dwErrCode], 0FD050F80h
0x1000e5c6  push    ecx; pftDueTime
0x1000e5c7  push    eax; pti
0x1000e5c8  mov     [esp+30h+var_4], 0FFFFFFFFh
0x1000e5d0  call    ds:__imp__SetThreadpoolTimer@16; SetThreadpoolTimer(x,x,x,x)
0x1000e5d6  mov     byte ptr [ebx], 1
0x1000e5d9  pop     edi
0x1000e5da  pop     esi
0x1000e5db  pop     ebx
0x1000e5dc  mov     esp, ebp
0x1000e5de  pop     ebp
0x1000e5df  retn    4
```
