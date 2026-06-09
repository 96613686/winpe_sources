# CacheUninitialize

- ea: `0x180433570`
- end: `0x180433681`
- name: `CacheUninitialize`
- size: `273`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180400eac`
- `0x18043341c`

## callees

- `0x1803ccff4`
- `0x18043298c`
- `0x180433570`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18043360b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180433624`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18043363d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18043360b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180433624`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18043363d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180433662`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180433662`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1804335dc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1804335dc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18043366f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18043366f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1804335ab`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1804335ab`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1804335bb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1804335bb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1804335c8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1804335c8`

## pseudocode

```c
void CacheUninitialize()
{
  g_fCRCacheInitialized = 0;
  if ( g_fCRCacheCSInitialized )
  {
    if ( CompiledRulesTimer )
    {
      _InterlockedExchange(&g_ThreadpoolTimerCount, 2);
      SetThreadpoolTimer(CompiledRulesTimer, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(CompiledRulesTimer, 1);
      CloseThreadpoolTimer(CompiledRulesTimer);
      CompiledRulesTimer = 0;
    }
    EnterCriticalSection(&g_CompiledRulesCacheCS);
    UnRegisterForChangeNotifications(g_dwTDONotificationHandle, g_dwCTPONotificationHandle);
    g_dwTDONotificationHandle = 0;
    g_dwCTPONotificationHandle = 0;
    if ( g_pSystemContainerDsName )
    {
      LocalFree(g_pSystemContainerDsName);
      g_pSystemContainerDsName = 0;
    }
    if ( g_pCTPContainerDsName )
    {
      LocalFree(g_pCTPContainerDsName);
      g_pCTPContainerDsName = 0;
    }
    if ( g_pTDOClassDsName )
    {
      LocalFree(g_pTDOClassDsName);
      g_pTDOClassDsName = 0;
    }
    HIDWORD(qword_180E54DB0) = 0;
    HIDWORD(qword_180E54D98) = 0;
    FreeHashTables();
    LeaveCriticalSection(&g_CompiledRulesCacheCS);
    DeleteCriticalSection(&g_CompiledRulesCacheCS);
    g_fCRCacheCSInitialized = 0;
  }
}

```

## disassembly

```asm
0x180433570  push    rbx
0x180433572  sub     rsp, 20h
0x180433576  xor     ebx, ebx
0x180433578  cmp     cs:?g_fCRCacheCSInitialized@@3HA, ebx; int g_fCRCacheCSInitialized
0x18043357e  mov     cs:?g_fCRCacheInitialized@@3HA, ebx; int g_fCRCacheInitialized
0x180433584  jz      loc_18043367B
0x18043358a  cmp     cs:?CompiledRulesTimer@@3PEAU_TP_TIMER@@EA, rbx; _TP_TIMER * CompiledRulesTimer
0x180433591  jz      short loc_1804335D5
0x180433593  lea     eax, [rbx+2]
0x180433596  xor     r9d, r9d; msWindowLength
0x180433599  xchg    eax, cs:?g_ThreadpoolTimerCount@@3JC; long volatile g_ThreadpoolTimerCount
0x18043359f  mov     rcx, cs:?CompiledRulesTimer@@3PEAU_TP_TIMER@@EA; pti
0x1804335a6  xor     r8d, r8d; msPeriod
0x1804335a9  xor     edx, edx; pftDueTime
0x1804335ab  call    cs:__imp_SetThreadpoolTimer
0x1804335b1  mov     rcx, cs:?CompiledRulesTimer@@3PEAU_TP_TIMER@@EA; pti
0x1804335b8  lea     edx, [rbx+1]; fCancelPendingCallbacks
0x1804335bb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1804335c1  mov     rcx, cs:?CompiledRulesTimer@@3PEAU_TP_TIMER@@EA; pti
0x1804335c8  call    cs:__imp_CloseThreadpoolTimer
0x1804335ce  mov     cs:?CompiledRulesTimer@@3PEAU_TP_TIMER@@EA, rbx; _TP_TIMER * CompiledRulesTimer
0x1804335d5  lea     rcx, ?g_CompiledRulesCacheCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1804335dc  call    cs:__imp_EnterCriticalSection
0x1804335e2  mov     edx, cs:?g_dwCTPONotificationHandle@@3KA; ulong g_dwCTPONotificationHandle
0x1804335e8  mov     ecx, cs:?g_dwTDONotificationHandle@@3KA; ulong g_dwTDONotificationHandle
0x1804335ee  call    UnRegisterForChangeNotifications
0x1804335f3  mov     rcx, cs:?g_pSystemContainerDsName@@3PEAU_DSNAME@@EA; hMem
0x1804335fa  mov     cs:?g_dwTDONotificationHandle@@3KA, ebx; ulong g_dwTDONotificationHandle
0x180433600  mov     cs:?g_dwCTPONotificationHandle@@3KA, ebx; ulong g_dwCTPONotificationHandle
0x180433606  test    rcx, rcx
0x180433609  jz      short loc_180433618
0x18043360b  call    cs:__imp_LocalFree
0x180433611  mov     cs:?g_pSystemContainerDsName@@3PEAU_DSNAME@@EA, rbx; _DSNAME * g_pSystemContainerDsName
0x180433618  mov     rcx, cs:?g_pCTPContainerDsName@@3PEAU_DSNAME@@EA; hMem
0x18043361f  test    rcx, rcx
0x180433622  jz      short loc_180433631
0x180433624  call    cs:__imp_LocalFree
0x18043362a  mov     cs:?g_pCTPContainerDsName@@3PEAU_DSNAME@@EA, rbx; _DSNAME * g_pCTPContainerDsName
0x180433631  mov     rcx, cs:?g_pTDOClassDsName@@3PEAU_DSNAME@@EA; hMem
0x180433638  test    rcx, rcx
0x18043363b  jz      short loc_18043364A
0x18043363d  call    cs:__imp_LocalFree
0x180433643  mov     cs:?g_pTDOClassDsName@@3PEAU_DSNAME@@EA, rbx; _DSNAME * g_pTDOClassDsName
0x18043364a  mov     dword ptr cs:qword_180E54DB0+4, ebx
0x180433650  mov     dword ptr cs:qword_180E54D98+4, ebx
0x180433656  call    ?FreeHashTables@@YAXXZ; FreeHashTables(void)
0x18043365b  lea     rcx, ?g_CompiledRulesCacheCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180433662  call    cs:__imp_LeaveCriticalSection
0x180433668  lea     rcx, ?g_CompiledRulesCacheCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18043366f  call    cs:__imp_DeleteCriticalSection
0x180433675  mov     cs:?g_fCRCacheCSInitialized@@3HA, ebx; int g_fCRCacheCSInitialized
0x18043367b  add     rsp, 20h
0x18043367f  pop     rbx
0x180433680  retn
```
