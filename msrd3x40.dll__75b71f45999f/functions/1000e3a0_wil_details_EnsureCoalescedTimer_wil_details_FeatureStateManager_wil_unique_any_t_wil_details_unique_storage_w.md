# wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<uint,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)

- ea: `0x1000e3a0`
- end: `0x1000e462`
- name: `??$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YGXAAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PAU_TP_TIMER@@P6GXPAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SGX0@ZU?$integral_constant@I$0A@@wistd@@PAU1@PAU1@$0A@$$T@details@wil@@@details@wil@@@1@AA_NPAVFeatureStateManager@01@@Z`
- size: `194`
- prototype: `int __stdcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1000cd70`

## callees

- `0x1000e3a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1000e417`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1000e427`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1000e417`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1000e427`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1000e3c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1000e3e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1000e3c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1000e3e8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1000e3fa`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1000e450`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1000e3fa`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1000e450`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1000e410`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1000e410`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1000e406`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1000e406`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1000e3d4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1000e3d4`

## pseudocode

```c
void __fastcall wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(
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
                          _lambda_a51444ad8368ae975c3855d6a9f2f637_::_lambda_invoker_stdcall_,
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
      dwErrCode.dwLowDateTime = 1294967296;
      dwErrCode.dwHighDateTime = -1;
      SetThreadpoolTimer(v6, &dwErrCode, 0, 0x124F8u);
      *a2 = 1;
    }
  }
}

```

## disassembly

```asm
0x1000e3a0  mov     edi, edi
0x1000e3a2  push    ebp
0x1000e3a3  mov     ebp, esp
0x1000e3a5  and     esp, 0FFFFFFF8h
0x1000e3a8  sub     esp, 14h
0x1000e3ab  push    ebx
0x1000e3ac  mov     ebx, edx
0x1000e3ae  push    esi
0x1000e3af  push    edi
0x1000e3b0  mov     edi, ecx
0x1000e3b2  cmp     byte ptr [ebx], 0
0x1000e3b5  jnz     loc_1000E459
0x1000e3bb  cmp     dword ptr [edi], 0
0x1000e3be  jnz     short loc_1000E42D
0x1000e3c0  call    ds:__imp__GetLastError@0; GetLastError()
0x1000e3c6  push    0; pcbe
0x1000e3c8  push    [ebp+pv]; pv
0x1000e3cb  mov     [esp+28h+dwErrCode], eax
0x1000e3cf  push    offset ?_lambda_invoker_stdcall_@_lambda_a51444ad8368ae975c3855d6a9f2f637_@@CG@PAU_TP_CALLBACK_INSTANCE@@PAXPAU_TP_TIMER@@@Z; pfnti
0x1000e3d4  call    ds:__imp__CreateThreadpoolTimer@12; CreateThreadpoolTimer(x,x,x)
0x1000e3da  mov     [esp+20h+var_C], eax
0x1000e3de  mov     eax, [edi]
0x1000e3e0  mov     [esp+20h+pti], eax
0x1000e3e4  test    eax, eax
0x1000e3e6  jz      short loc_1000E41D
0x1000e3e8  call    ds:__imp__GetLastError@0; GetLastError()
0x1000e3ee  push    0; msWindowLength
0x1000e3f0  push    0; msPeriod
0x1000e3f2  push    0; pftDueTime
0x1000e3f4  push    [esp+2Ch+pti]; pti
0x1000e3f8  mov     esi, eax
0x1000e3fa  call    ds:__imp__SetThreadpoolTimer@16; SetThreadpoolTimer(x,x,x,x)
0x1000e400  push    1; fCancelPendingCallbacks
0x1000e402  push    [esp+24h+pti]; pti
0x1000e406  call    ds:__imp__WaitForThreadpoolTimerCallbacks@8; WaitForThreadpoolTimerCallbacks(x,x)
0x1000e40c  push    [esp+20h+pti]; pti
0x1000e410  call    ds:__imp__CloseThreadpoolTimer@4; CloseThreadpoolTimer(x)
0x1000e416  push    esi; dwErrCode
0x1000e417  call    ds:__imp__SetLastError@4; SetLastError(x)
0x1000e41d  mov     eax, [esp+20h+var_C]
0x1000e421  push    [esp+20h+dwErrCode]; dwErrCode
0x1000e425  mov     [edi], eax
0x1000e427  call    ds:__imp__SetLastError@4; SetLastError(x)
0x1000e42d  mov     eax, [edi]
0x1000e42f  test    eax, eax
0x1000e431  jz      short loc_1000E459
0x1000e433  push    124F8h; msWindowLength
0x1000e438  push    0; msPeriod
0x1000e43a  lea     ecx, [esp+28h+dwErrCode]
0x1000e43e  mov     [esp+28h+dwErrCode], 4D2FA200h
0x1000e446  push    ecx; pftDueTime
0x1000e447  push    eax; pti
0x1000e448  mov     [esp+30h+var_4], 0FFFFFFFFh
0x1000e450  call    ds:__imp__SetThreadpoolTimer@16; SetThreadpoolTimer(x,x,x,x)
0x1000e456  mov     byte ptr [ebx], 1
0x1000e459  pop     edi
0x1000e45a  pop     esi
0x1000e45b  pop     ebx
0x1000e45c  mov     esp, ebp
0x1000e45e  pop     ebp
0x1000e45f  retn    4
```
