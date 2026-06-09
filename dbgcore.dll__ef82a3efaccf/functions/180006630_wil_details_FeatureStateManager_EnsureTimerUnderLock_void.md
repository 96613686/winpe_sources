# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180006630`
- end: `0x180006704`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800090c4`

## callees

- `0x180006630`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006656`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000667d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006656`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000667d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800066af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800066bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800066af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800066bb`
- `api-ms-win-core-threadpool-l1-1-0!WaitForThreadpoolTimerCallbacks` at `0x18000669e`
- `api-ms-win-core-threadpool-l1-1-0!WaitForThreadpoolTimerCallbacks` at `0x18000669e`
- `api-ms-win-core-threadpool-l1-1-0!CloseThreadpoolTimer` at `0x1800066a7`
- `api-ms-win-core-threadpool-l1-1-0!CloseThreadpoolTimer` at `0x1800066a7`
- `api-ms-win-core-threadpool-l1-1-0!SetThreadpoolTimer` at `0x180006690`
- `api-ms-win-core-threadpool-l1-1-0!SetThreadpoolTimer` at `0x1800066e7`
- `api-ms-win-core-threadpool-l1-1-0!SetThreadpoolTimer` at `0x180006690`
- `api-ms-win-core-threadpool-l1-1-0!SetThreadpoolTimer` at `0x1800066e7`
- `api-ms-win-core-threadpool-l1-1-0!CreateThreadpoolTimer` at `0x18000666b`
- `api-ms-win-core-threadpool-l1-1-0!CreateThreadpoolTimer` at `0x18000666b`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::EnsureTimerUnderLock(struct _TP_TIMER **pv)
{
  DWORD LastError; // ebp
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v4; // rsi
  PTP_TIMER v5; // r14
  DWORD v6; // ebx
  struct _TP_TIMER *v7; // rcx
  struct _FILETIME pftDueTime; // [rsp+40h] [rbp+8h] BYREF

  if ( !*((_BYTE *)pv + 65) )
  {
    if ( !pv[6] )
    {
      LastError = GetLastError();
      ThreadpoolTimer = CreateThreadpoolTimer(_lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_, pv, 0);
      v4 = pv[6];
      v5 = ThreadpoolTimer;
      if ( v4 )
      {
        v6 = GetLastError();
        SetThreadpoolTimer(v4, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v4, 1);
        CloseThreadpoolTimer(v4);
        SetLastError(v6);
      }
      pv[6] = v5;
      SetLastError(LastError);
    }
    v7 = pv[6];
    if ( v7 )
    {
      pftDueTime = (struct _FILETIME)-3000000000LL;
      SetThreadpoolTimer(v7, &pftDueTime, 0, 0x124F8u);
      *((_BYTE *)pv + 65) = 1;
    }
  }
}

```

## disassembly

```asm
0x180006630  mov     [rsp+arg_8], rbx
0x180006635  mov     [rsp+arg_10], rbp
0x18000663a  push    rsi
0x18000663b  push    rdi
0x18000663c  push    r14
0x18000663e  sub     rsp, 20h
0x180006642  cmp     byte ptr [rcx+41h], 0
0x180006646  mov     rdi, rcx
0x180006649  jnz     loc_1800066F1
0x18000664f  cmp     qword ptr [rcx+30h], 0
0x180006654  jnz     short loc_1800066C1
0x180006656  call    cs:__imp_GetLastError
0x18000665c  xor     r8d, r8d; pcbe
0x18000665f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180006666  mov     rdx, rdi; pv
0x180006669  mov     ebp, eax
0x18000666b  call    cs:__imp_CreateThreadpoolTimer
0x180006671  mov     rsi, [rdi+30h]
0x180006675  mov     r14, rax
0x180006678  test    rsi, rsi
0x18000667b  jz      short loc_1800066B5
0x18000667d  call    cs:__imp_GetLastError
0x180006683  xor     r9d, r9d; msWindowLength
0x180006686  xor     r8d, r8d; msPeriod
0x180006689  xor     edx, edx; pftDueTime
0x18000668b  mov     rcx, rsi; pti
0x18000668e  mov     ebx, eax
0x180006690  call    cs:__imp_SetThreadpoolTimer
0x180006696  mov     edx, 1; fCancelPendingCallbacks
0x18000669b  mov     rcx, rsi; pti
0x18000669e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800066a4  mov     rcx, rsi; pti
0x1800066a7  call    cs:__imp_CloseThreadpoolTimer
0x1800066ad  mov     ecx, ebx; dwErrCode
0x1800066af  call    cs:__imp_SetLastError
0x1800066b5  mov     ecx, ebp; dwErrCode
0x1800066b7  mov     [rdi+30h], r14
0x1800066bb  call    cs:__imp_SetLastError
0x1800066c1  mov     rcx, [rdi+30h]; pti
0x1800066c5  test    rcx, rcx
0x1800066c8  jz      short loc_1800066F1
0x1800066ca  mov     rax, 0FFFFFFFF4D2FA200h
0x1800066d4  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x1800066d9  mov     r9d, 124F8h; msWindowLength
0x1800066df  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x1800066e4  xor     r8d, r8d; msPeriod
0x1800066e7  call    cs:__imp_SetThreadpoolTimer
0x1800066ed  mov     byte ptr [rdi+41h], 1
0x1800066f1  mov     rbx, [rsp+38h+arg_8]
0x1800066f6  mov     rbp, [rsp+38h+arg_10]
0x1800066fb  add     rsp, 20h
0x1800066ff  pop     r14
0x180006701  pop     rdi
0x180006702  pop     rsi
0x180006703  retn
```
