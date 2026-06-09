# CryptnetUrlCacheSvcServiceStop

- ea: `0x18000c8b4`
- end: `0x18000ca0a`
- name: `CryptnetUrlCacheSvcServiceStop`
- size: `342`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a690`

## callees

- `0x180001824`
- `0x1800068f0`
- `0x18000a660`
- `0x18000c8b4`
- `0x18000fbec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c968`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c998`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c968`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c998`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c983`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c983`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c9ea`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c9ea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c8d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c93f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c8d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c93f`
- `CRYPT32!I_CryptFreeLruCache` at `0x18000c9c2`
- `CRYPT32!I_CryptFreeLruCache` at `0x18000c9c2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000c919`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000c919`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000c9e1`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000c9e1`

## pseudocode

```c
__int64 CryptnetUrlCacheSvcServiceStop()
{
  unsigned int v0; // ebx
  __int64 result; // rax
  HLOCAL v2; // rdi

  v0 = 1;
  if ( _InterlockedExchange(&lUrlCacheSvcStartOrStop, 1) )
  {
    SetLastError(0x426u);
    return 0;
  }
  if ( fUrlCacheSvcStarted )
  {
    fUrlCacheSvcStarted = 0;
    _InterlockedAdd(&lUrlCacheSvcActiveRefCnt, 1u);
    if ( _InterlockedExchangeAdd(&lUrlCacheSvcActiveRefCnt, 0xFFFFFFFF) == 1
      || (Sleep(0x64u),
          _InterlockedAdd(&lUrlCacheSvcActiveRefCnt, 1u),
          _InterlockedExchangeAdd(&lUrlCacheSvcActiveRefCnt, 0xFFFFFFFF) == 1) )
    {
      while ( 1 )
      {
        EnterCriticalSection(&JobsCriticalSection);
        v2 = pPendingLogoffExitJobHead;
        if ( !pPendingLogoffExitJobHead )
          break;
        *((_DWORD *)pPendingLogoffExitJobHead + 16) = 1;
        RemoveFromLinkList(&pPendingLogoffExitJobHead, v2, 0);
        LeaveCriticalSection(&JobsCriticalSection);
        AddToBeRunJobEx((FILETIME)v2, 4, 0, 0);
      }
      LeaveCriticalSection(&JobsCriticalSection);
      if ( (unsigned int)CreateAndAddToBeRunServiceStopJob() )
      {
        if ( hPreFetchJobLruCache )
        {
          I_CryptFreeLruCache(hPreFetchJobLruCache, 0, 0);
          hPreFetchJobLruCache = 0;
        }
        FreePendingHpkp();
        BCryptCloseAlgorithmProvider(hAlgSha256, 0);
        DeleteCriticalSection(&JobsCriticalSection);
        goto LABEL_16;
      }
      fUrlCacheSvcStarted = 1;
    }
    else
    {
      fUrlCacheSvcStarted = 1;
      SetLastError(0x8000000A);
    }
    v0 = 0;
  }
LABEL_16:
  result = v0;
  _InterlockedExchange(&lUrlCacheSvcStartOrStop, 0);
  return result;
}

```

## disassembly

```asm
0x18000c8b4  mov     [rsp+arg_0], rbx
0x18000c8b9  mov     [rsp+arg_8], rsi
0x18000c8be  push    rdi
0x18000c8bf  sub     rsp, 20h
0x18000c8c3  mov     ebx, 1
0x18000c8c8  mov     eax, ebx
0x18000c8ca  xchg    eax, cs:?lUrlCacheSvcStartOrStop@@3JC; long volatile lUrlCacheSvcStartOrStop
0x18000c8d0  test    eax, eax
0x18000c8d2  jz      short loc_18000C8E6
0x18000c8d4  mov     ecx, 426h; dwErrCode
0x18000c8d9  call    cs:__imp_SetLastError
0x18000c8df  xor     eax, eax
0x18000c8e1  jmp     loc_18000C9FA
0x18000c8e6  mov     eax, cs:?fUrlCacheSvcStarted@@3HC; int volatile fUrlCacheSvcStarted
0x18000c8ec  test    eax, eax
0x18000c8ee  jz      loc_18000C9F0
0x18000c8f4  mov     cs:?fUrlCacheSvcStarted@@3HC, 0; int volatile fUrlCacheSvcStarted
0x18000c8fe  lock add cs:?lUrlCacheSvcActiveRefCnt@@3JC, ebx; long volatile lUrlCacheSvcActiveRefCnt
0x18000c905  or      edi, 0FFFFFFFFh
0x18000c908  mov     eax, edi
0x18000c90a  lock xadd cs:?lUrlCacheSvcActiveRefCnt@@3JC, eax; long volatile lUrlCacheSvcActiveRefCnt
0x18000c912  add     eax, edi
0x18000c914  jz      short loc_18000C947
0x18000c916  lea     ecx, [rdi+65h]; dwMilliseconds
0x18000c919  call    cs:__imp_Sleep
0x18000c91f  lock add cs:?lUrlCacheSvcActiveRefCnt@@3JC, ebx; long volatile lUrlCacheSvcActiveRefCnt
0x18000c926  mov     eax, edi
0x18000c928  lock xadd cs:?lUrlCacheSvcActiveRefCnt@@3JC, eax; long volatile lUrlCacheSvcActiveRefCnt
0x18000c930  add     eax, edi
0x18000c932  jz      short loc_18000C947
0x18000c934  mov     cs:?fUrlCacheSvcStarted@@3HC, ebx; int volatile fUrlCacheSvcStarted
0x18000c93a  mov     ecx, 8000000Ah; dwErrCode
0x18000c93f  call    cs:__imp_SetLastError
0x18000c945  jmp     short loc_18000C9AD
0x18000c947  lea     rsi, ?JobsCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION JobsCriticalSection
0x18000c94e  jmp     short loc_18000C980
0x18000c950  xor     r8d, r8d
0x18000c953  mov     [rdi+40h], ebx
0x18000c956  mov     rdx, rdi
0x18000c959  lea     rcx, ?pPendingLogoffExitJobHead@@3PEAU_CUCS_LOGOFF_EXIT_JOB_ENTRY@@EA; _CUCS_LOGOFF_EXIT_JOB_ENTRY * pPendingLogoffExitJobHead
0x18000c960  call    RemoveFromLinkList
0x18000c965  mov     rcx, rsi; lpCriticalSection
0x18000c968  call    cs:__imp_LeaveCriticalSection
0x18000c96e  xor     r9d, r9d
0x18000c971  xor     r8d, r8d
0x18000c974  mov     rcx, rdi
0x18000c977  lea     edx, [r9+4]
0x18000c97b  call    AddToBeRunJobEx
0x18000c980  mov     rcx, rsi; lpCriticalSection
0x18000c983  call    cs:__imp_EnterCriticalSection
0x18000c989  mov     rdi, cs:?pPendingLogoffExitJobHead@@3PEAU_CUCS_LOGOFF_EXIT_JOB_ENTRY@@EA; _CUCS_LOGOFF_EXIT_JOB_ENTRY * pPendingLogoffExitJobHead
0x18000c990  test    rdi, rdi
0x18000c993  jnz     short loc_18000C950
0x18000c995  mov     rcx, rsi; lpCriticalSection
0x18000c998  call    cs:__imp_LeaveCriticalSection
0x18000c99e  call    CreateAndAddToBeRunServiceStopJob
0x18000c9a3  test    eax, eax
0x18000c9a5  jnz     short loc_18000C9B1
0x18000c9a7  mov     cs:?fUrlCacheSvcStarted@@3HC, ebx; int volatile fUrlCacheSvcStarted
0x18000c9ad  xor     ebx, ebx
0x18000c9af  jmp     short loc_18000C9F0
0x18000c9b1  mov     rcx, cs:?hPreFetchJobLruCache@@3PEAXEA; void * hPreFetchJobLruCache
0x18000c9b8  test    rcx, rcx
0x18000c9bb  jz      short loc_18000C9D3
0x18000c9bd  xor     r8d, r8d
0x18000c9c0  xor     edx, edx
0x18000c9c2  call    cs:__imp_I_CryptFreeLruCache
0x18000c9c8  mov     cs:?hPreFetchJobLruCache@@3PEAXEA, 0; void * hPreFetchJobLruCache
0x18000c9d3  call    FreePendingHpkp
0x18000c9d8  mov     rcx, cs:?hAlgSha256@@3PEAXEA; hAlgorithm
0x18000c9df  xor     edx, edx; dwFlags
0x18000c9e1  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18000c9e7  mov     rcx, rsi; lpCriticalSection
0x18000c9ea  call    cs:__imp_DeleteCriticalSection
0x18000c9f0  xor     ecx, ecx
0x18000c9f2  mov     eax, ebx
0x18000c9f4  xchg    ecx, cs:?lUrlCacheSvcStartOrStop@@3JC; long volatile lUrlCacheSvcStartOrStop
0x18000c9fa  mov     rbx, [rsp+28h+arg_0]
0x18000c9ff  mov     rsi, [rsp+28h+arg_8]
0x18000ca04  add     rsp, 20h
0x18000ca08  pop     rdi
0x18000ca09  retn
```
