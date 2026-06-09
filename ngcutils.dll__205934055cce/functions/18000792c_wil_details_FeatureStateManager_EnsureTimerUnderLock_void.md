# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x18000792c`
- end: `0x180007a00`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180009534`

## callees

- `0x18000792c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800079ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800079b7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800079ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800079b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007952`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007979`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007952`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007979`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000798c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800079e3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000798c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800079e3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180007967`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180007967`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800079a3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800079a3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000799a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000799a`

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
      ThreadpoolTimer = CreateThreadpoolTimer(
                          `wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
                          pv,
                          0);
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
0x18000792c  mov     [rsp+arg_8], rbx
0x180007931  mov     [rsp+arg_10], rbp
0x180007936  push    rsi
0x180007937  push    rdi
0x180007938  push    r14
0x18000793a  sub     rsp, 20h
0x18000793e  cmp     byte ptr [rcx+41h], 0
0x180007942  mov     rdi, rcx
0x180007945  jnz     loc_1800079ED
0x18000794b  cmp     qword ptr [rcx+30h], 0
0x180007950  jnz     short loc_1800079BD
0x180007952  call    cs:__imp_GetLastError
0x180007958  xor     r8d, r8d; pcbe
0x18000795b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180007962  mov     rdx, rdi; pv
0x180007965  mov     ebp, eax
0x180007967  call    cs:__imp_CreateThreadpoolTimer
0x18000796d  mov     rsi, [rdi+30h]
0x180007971  mov     r14, rax
0x180007974  test    rsi, rsi
0x180007977  jz      short loc_1800079B1
0x180007979  call    cs:__imp_GetLastError
0x18000797f  xor     r9d, r9d; msWindowLength
0x180007982  xor     r8d, r8d; msPeriod
0x180007985  xor     edx, edx; pftDueTime
0x180007987  mov     rcx, rsi; pti
0x18000798a  mov     ebx, eax
0x18000798c  call    cs:__imp_SetThreadpoolTimer
0x180007992  mov     edx, 1; fCancelPendingCallbacks
0x180007997  mov     rcx, rsi; pti
0x18000799a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800079a0  mov     rcx, rsi; pti
0x1800079a3  call    cs:__imp_CloseThreadpoolTimer
0x1800079a9  mov     ecx, ebx; dwErrCode
0x1800079ab  call    cs:__imp_SetLastError
0x1800079b1  mov     ecx, ebp; dwErrCode
0x1800079b3  mov     [rdi+30h], r14
0x1800079b7  call    cs:__imp_SetLastError
0x1800079bd  mov     rcx, [rdi+30h]; pti
0x1800079c1  test    rcx, rcx
0x1800079c4  jz      short loc_1800079ED
0x1800079c6  mov     rax, 0FFFFFFFF4D2FA200h
0x1800079d0  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x1800079d5  mov     r9d, 124F8h; msWindowLength
0x1800079db  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x1800079e0  xor     r8d, r8d; msPeriod
0x1800079e3  call    cs:__imp_SetThreadpoolTimer
0x1800079e9  mov     byte ptr [rdi+41h], 1
0x1800079ed  mov     rbx, [rsp+38h+arg_8]
0x1800079f2  mov     rbp, [rsp+38h+arg_10]
0x1800079f7  add     rsp, 20h
0x1800079fb  pop     r14
0x1800079fd  pop     rdi
0x1800079fe  pop     rsi
0x1800079ff  retn
```
