# _CatDBStopChangeNotifications(void)

- ea: `0x180013320`
- end: `0x180013413`
- name: `?_CatDBStopChangeNotifications@@YAXXZ`
- size: `243`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ad54`
- `0x1800131b8`

## callees

- `0x18000c7e8`
- `0x180012d9c`
- `0x180013320`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800133db`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800133db`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800133bc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800133bc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800133af`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800133af`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180013380`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180013380`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001338d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001338d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001336e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001336e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180013349`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180013349`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18001333c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18001333c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800133e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800133f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800133e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800133f5`

## pseudocode

```c
void _CatDBStopChangeNotifications(void)
{
  g_CatalogChangesShuttingDown = 1;
  if ( g_CatrootChangesWait )
  {
    WaitForThreadpoolWaitCallbacks(g_CatrootChangesWait, 1);
    CloseThreadpoolWait(g_CatrootChangesWait);
    g_CatrootChangesWait = 0;
  }
  if ( g_DrainIgnoreListTimer )
  {
    SetThreadpoolTimer(g_DrainIgnoreListTimer, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(g_DrainIgnoreListTimer, 1);
    CloseThreadpoolTimer(g_DrainIgnoreListTimer);
    g_DrainIgnoreListTimer = 0;
  }
  if ( g_CatrootSyncWork )
  {
    WaitForThreadpoolWorkCallbacks(g_CatrootSyncWork, 1);
    CloseThreadpoolWork(g_CatrootSyncWork);
    g_CatrootSyncWork = 0;
  }
  ExpireIgnoreListEntries(0);
  DeleteCriticalSection(&g_IgnoreListCS);
  CloseHandle(hObject);
  CloseHandle(g_CatrootChangesWaitContext);
  memset_0(&g_CatrootChangesWaitContext, 0, 0x1028u);
}

```

## disassembly

```asm
0x180013320  sub     rsp, 28h
0x180013324  mov     rcx, cs:?g_CatrootChangesWait@@3PEAU_TP_WAIT@@EA; pwa
0x18001332b  mov     cs:?g_CatalogChangesShuttingDown@@3EA, 1; uchar g_CatalogChangesShuttingDown
0x180013332  test    rcx, rcx
0x180013335  jz      short loc_18001335A
0x180013337  mov     edx, 1; fCancelPendingCallbacks
0x18001333c  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180013342  mov     rcx, cs:?g_CatrootChangesWait@@3PEAU_TP_WAIT@@EA; pwa
0x180013349  call    cs:__imp_CloseThreadpoolWait
0x18001334f  mov     cs:?g_CatrootChangesWait@@3PEAU_TP_WAIT@@EA, 0; _TP_WAIT * g_CatrootChangesWait
0x18001335a  mov     rcx, cs:?g_DrainIgnoreListTimer@@3PEAU_TP_TIMER@@EA; pti
0x180013361  test    rcx, rcx
0x180013364  jz      short loc_18001339E
0x180013366  xor     r9d, r9d; msWindowLength
0x180013369  xor     r8d, r8d; msPeriod
0x18001336c  xor     edx, edx; pftDueTime
0x18001336e  call    cs:__imp_SetThreadpoolTimer
0x180013374  mov     rcx, cs:?g_DrainIgnoreListTimer@@3PEAU_TP_TIMER@@EA; pti
0x18001337b  mov     edx, 1; fCancelPendingCallbacks
0x180013380  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180013386  mov     rcx, cs:?g_DrainIgnoreListTimer@@3PEAU_TP_TIMER@@EA; pti
0x18001338d  call    cs:__imp_CloseThreadpoolTimer
0x180013393  mov     cs:?g_DrainIgnoreListTimer@@3PEAU_TP_TIMER@@EA, 0; _TP_TIMER * g_DrainIgnoreListTimer
0x18001339e  mov     rcx, cs:?g_CatrootSyncWork@@3PEAU_TP_WORK@@EA; pwk
0x1800133a5  test    rcx, rcx
0x1800133a8  jz      short loc_1800133CD
0x1800133aa  mov     edx, 1; fCancelPendingCallbacks
0x1800133af  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1800133b5  mov     rcx, cs:?g_CatrootSyncWork@@3PEAU_TP_WORK@@EA; pwk
0x1800133bc  call    cs:__imp_CloseThreadpoolWork
0x1800133c2  mov     cs:?g_CatrootSyncWork@@3PEAU_TP_WORK@@EA, 0; _TP_WORK * g_CatrootSyncWork
0x1800133cd  xor     ecx, ecx
0x1800133cf  call    ExpireIgnoreListEntries
0x1800133d4  lea     rcx, ?g_IgnoreListCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800133db  call    cs:__imp_DeleteCriticalSection
0x1800133e1  mov     rcx, cs:hObject; hObject
0x1800133e8  call    cs:__imp_CloseHandle
0x1800133ee  mov     rcx, cs:?g_CatrootChangesWaitContext@@3UCATDB_CHANGES_WAIT_CONTEXT@@A; hObject
0x1800133f5  call    cs:__imp_CloseHandle
0x1800133fb  xor     edx, edx; Val
0x1800133fd  lea     rcx, ?g_CatrootChangesWaitContext@@3UCATDB_CHANGES_WAIT_CONTEXT@@A; void *
0x180013404  mov     r8d, 1028h; Size
0x18001340a  add     rsp, 28h
0x18001340e  jmp     memset_0
```
