# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x1800068fc`
- end: `0x1800069d0`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180008424`

## callees

- `0x1800068fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000697b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006987`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000697b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006987`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006922`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006949`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006922`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006949`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000695c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800069b3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000695c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800069b3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180006937`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180006937`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006973`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006973`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000696a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000696a`

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
                          (PTP_TIMER_CALLBACK)`wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
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
0x1800068fc  mov     [rsp+arg_8], rbx
0x180006901  mov     [rsp+arg_10], rbp
0x180006906  push    rsi
0x180006907  push    rdi
0x180006908  push    r14
0x18000690a  sub     rsp, 20h
0x18000690e  cmp     byte ptr [rcx+41h], 0
0x180006912  mov     rdi, rcx
0x180006915  jnz     loc_1800069BD
0x18000691b  cmp     qword ptr [rcx+30h], 0
0x180006920  jnz     short loc_18000698D
0x180006922  call    cs:__imp_GetLastError
0x180006928  xor     r8d, r8d; pcbe
0x18000692b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180006932  mov     rdx, rdi; pv
0x180006935  mov     ebp, eax
0x180006937  call    cs:__imp_CreateThreadpoolTimer
0x18000693d  mov     rsi, [rdi+30h]
0x180006941  mov     r14, rax
0x180006944  test    rsi, rsi
0x180006947  jz      short loc_180006981
0x180006949  call    cs:__imp_GetLastError
0x18000694f  xor     r9d, r9d; msWindowLength
0x180006952  xor     r8d, r8d; msPeriod
0x180006955  xor     edx, edx; pftDueTime
0x180006957  mov     rcx, rsi; pti
0x18000695a  mov     ebx, eax
0x18000695c  call    cs:__imp_SetThreadpoolTimer
0x180006962  mov     edx, 1; fCancelPendingCallbacks
0x180006967  mov     rcx, rsi; pti
0x18000696a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006970  mov     rcx, rsi; pti
0x180006973  call    cs:__imp_CloseThreadpoolTimer
0x180006979  mov     ecx, ebx; dwErrCode
0x18000697b  call    cs:__imp_SetLastError
0x180006981  mov     ecx, ebp; dwErrCode
0x180006983  mov     [rdi+30h], r14
0x180006987  call    cs:__imp_SetLastError
0x18000698d  mov     rcx, [rdi+30h]; pti
0x180006991  test    rcx, rcx
0x180006994  jz      short loc_1800069BD
0x180006996  mov     rax, 0FFFFFFFF4D2FA200h
0x1800069a0  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x1800069a5  mov     r9d, 124F8h; msWindowLength
0x1800069ab  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x1800069b0  xor     r8d, r8d; msPeriod
0x1800069b3  call    cs:__imp_SetThreadpoolTimer
0x1800069b9  mov     byte ptr [rdi+41h], 1
0x1800069bd  mov     rbx, [rsp+38h+arg_8]
0x1800069c2  mov     rbp, [rsp+38h+arg_10]
0x1800069c7  add     rsp, 20h
0x1800069cb  pop     r14
0x1800069cd  pop     rdi
0x1800069ce  pop     rsi
0x1800069cf  retn
```
