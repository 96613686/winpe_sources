# wil::details::FeatureStateManager::EnsureSRUMTimerUnderLock(void)

- ea: `0x18000b5e8`
- end: `0x18000b6d2`
- name: `?EnsureSRUMTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `234`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d850`

## callees

- `0x1800067c0`
- `0x18000b5e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b676`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b682`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b676`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b682`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b61d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b644`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b61d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b644`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000b632`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000b632`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b66e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b66e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b665`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b665`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b657`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b6a8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b657`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b6a8`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::EnsureSRUMTimerUnderLock(struct _TP_TIMER **pv)
{
  DWORD LastError; // ebp
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v4; // rsi
  PTP_TIMER v5; // r14
  DWORD v6; // ebx
  struct _TP_TIMER *v7; // rcx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-28h] BYREF

  if ( !*((_BYTE *)pv + 64) )
  {
    if ( !pv[7] )
    {
      LastError = GetLastError();
      ThreadpoolTimer = CreateThreadpoolTimer(_lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_, pv, 0);
      v4 = pv[7];
      v5 = ThreadpoolTimer;
      if ( v4 )
      {
        v6 = GetLastError();
        SetThreadpoolTimer(v4, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v4, 1);
        CloseThreadpoolTimer(v4);
        SetLastError(v6);
      }
      pv[7] = v5;
      SetLastError(LastError);
    }
    v7 = pv[7];
    if ( v7 )
    {
      pftDueTime = (struct _FILETIME)-50000000LL;
      SetThreadpoolTimer(v7, &pftDueTime, 0, 0x4E2u);
      *((_BYTE *)pv + 64) = 1;
    }
  }
}

```

## disassembly

```asm
0x18000b5e8  mov     [rsp+arg_8], rbx
0x18000b5ed  mov     [rsp+arg_10], rbp
0x18000b5f2  push    rsi
0x18000b5f3  push    rdi
0x18000b5f4  push    r14
0x18000b5f6  sub     rsp, 30h
0x18000b5fa  mov     rax, cs:__security_cookie
0x18000b601  xor     rax, rsp
0x18000b604  mov     [rsp+48h+var_20], rax
0x18000b609  cmp     byte ptr [rcx+40h], 0
0x18000b60d  mov     rdi, rcx
0x18000b610  jnz     loc_18000B6B2
0x18000b616  cmp     qword ptr [rcx+38h], 0
0x18000b61b  jnz     short loc_18000B688
0x18000b61d  call    cs:__imp_GetLastError
0x18000b623  xor     r8d, r8d; pcbe
0x18000b626  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000b62d  mov     rdx, rdi; pv
0x18000b630  mov     ebp, eax
0x18000b632  call    cs:__imp_CreateThreadpoolTimer
0x18000b638  mov     rsi, [rdi+38h]
0x18000b63c  mov     r14, rax
0x18000b63f  test    rsi, rsi
0x18000b642  jz      short loc_18000B67C
0x18000b644  call    cs:__imp_GetLastError
0x18000b64a  xor     r9d, r9d; msWindowLength
0x18000b64d  xor     r8d, r8d; msPeriod
0x18000b650  xor     edx, edx; pftDueTime
0x18000b652  mov     rcx, rsi; pti
0x18000b655  mov     ebx, eax
0x18000b657  call    cs:__imp_SetThreadpoolTimer
0x18000b65d  mov     edx, 1; fCancelPendingCallbacks
0x18000b662  mov     rcx, rsi; pti
0x18000b665  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000b66b  mov     rcx, rsi; pti
0x18000b66e  call    cs:__imp_CloseThreadpoolTimer
0x18000b674  mov     ecx, ebx; dwErrCode
0x18000b676  call    cs:__imp_SetLastError
0x18000b67c  mov     ecx, ebp; dwErrCode
0x18000b67e  mov     [rdi+38h], r14
0x18000b682  call    cs:__imp_SetLastError
0x18000b688  mov     rcx, [rdi+38h]; pti
0x18000b68c  test    rcx, rcx
0x18000b68f  jz      short loc_18000B6B2
0x18000b691  mov     r9d, 4E2h; msWindowLength
0x18000b697  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000b6a0  xor     r8d, r8d; msPeriod
0x18000b6a3  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x18000b6a8  call    cs:__imp_SetThreadpoolTimer
0x18000b6ae  mov     byte ptr [rdi+40h], 1
0x18000b6b2  mov     rcx, [rsp+48h+var_20]
0x18000b6b7  xor     rcx, rsp; StackCookie
0x18000b6ba  call    __security_check_cookie
0x18000b6bf  mov     rbx, [rsp+48h+arg_8]
0x18000b6c4  mov     rbp, [rsp+48h+arg_10]
0x18000b6c9  add     rsp, 30h
0x18000b6cd  pop     r14
0x18000b6cf  pop     rdi
0x18000b6d0  pop     rsi
0x18000b6d1  retn
```
