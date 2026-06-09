# CscService_DestroyGlobalThreadSyncObjects(void)

- ea: `0x180054d80`
- end: `0x180054e5d`
- name: `?CscService_DestroyGlobalThreadSyncObjects@@YAXXZ`
- size: `221`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180054340`
- `0x180054c68`

## callees

- `0x180054d80`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054d90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054dad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054dca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054e47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054d90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054dad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054dca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054e47`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180054deb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180054e0b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180054e2b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180054deb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180054e0b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180054e2b`

## pseudocode

```c
void CscService_DestroyGlobalThreadSyncObjects(void)
{
  if ( g_hevtReady )
  {
    CloseHandle(g_hevtReady);
    g_hevtReady = 0;
  }
  if ( g_hevtStop )
  {
    CloseHandle(g_hevtStop);
    g_hevtStop = 0;
  }
  if ( g_hevtDone )
  {
    CloseHandle(g_hevtDone);
    g_hevtDone = 0;
  }
  if ( g_bPrefetchCloseHandleCritSecInitialized )
  {
    DeleteCriticalSection(&g_csPrefetchCloseHandle);
    g_bPrefetchCloseHandleCritSecInitialized = 0;
  }
  if ( g_bDoneCritSecInitialized )
  {
    DeleteCriticalSection(&g_csDone);
    g_bDoneCritSecInitialized = 0;
  }
  if ( g_bAdminPinCritSecInitialized )
  {
    DeleteCriticalSection(&g_csAdminPin);
    g_bAdminPinCritSecInitialized = 0;
  }
  if ( g_hthdPreShutdownCleanup )
  {
    CloseHandle(g_hthdPreShutdownCleanup);
    g_hthdPreShutdownCleanup = 0;
  }
}

```

## disassembly

```asm
0x180054d80  sub     rsp, 28h
0x180054d84  mov     rcx, cs:?g_hevtReady@@3PEAXEA; hObject
0x180054d8b  test    rcx, rcx
0x180054d8e  jz      short loc_180054DA1
0x180054d90  call    cs:__imp_CloseHandle
0x180054d96  mov     cs:?g_hevtReady@@3PEAXEA, 0; void * g_hevtReady
0x180054da1  mov     rcx, cs:?g_hevtStop@@3PEAXEA; hObject
0x180054da8  test    rcx, rcx
0x180054dab  jz      short loc_180054DBE
0x180054dad  call    cs:__imp_CloseHandle
0x180054db3  mov     cs:?g_hevtStop@@3PEAXEA, 0; void * g_hevtStop
0x180054dbe  mov     rcx, cs:?g_hevtDone@@3PEAXEA; hObject
0x180054dc5  test    rcx, rcx
0x180054dc8  jz      short loc_180054DDB
0x180054dca  call    cs:__imp_CloseHandle
0x180054dd0  mov     cs:?g_hevtDone@@3PEAXEA, 0; void * g_hevtDone
0x180054ddb  cmp     cs:?g_bPrefetchCloseHandleCritSecInitialized@@3HA, 0; int g_bPrefetchCloseHandleCritSecInitialized
0x180054de2  jz      short loc_180054DFB
0x180054de4  lea     rcx, ?g_csPrefetchCloseHandle@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180054deb  call    cs:__imp_DeleteCriticalSection
0x180054df1  mov     cs:?g_bPrefetchCloseHandleCritSecInitialized@@3HA, 0; int g_bPrefetchCloseHandleCritSecInitialized
0x180054dfb  cmp     cs:?g_bDoneCritSecInitialized@@3HA, 0; int g_bDoneCritSecInitialized
0x180054e02  jz      short loc_180054E1B
0x180054e04  lea     rcx, ?g_csDone@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180054e0b  call    cs:__imp_DeleteCriticalSection
0x180054e11  mov     cs:?g_bDoneCritSecInitialized@@3HA, 0; int g_bDoneCritSecInitialized
0x180054e1b  cmp     cs:?g_bAdminPinCritSecInitialized@@3HA, 0; int g_bAdminPinCritSecInitialized
0x180054e22  jz      short loc_180054E3B
0x180054e24  lea     rcx, ?g_csAdminPin@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180054e2b  call    cs:__imp_DeleteCriticalSection
0x180054e31  mov     cs:?g_bAdminPinCritSecInitialized@@3HA, 0; int g_bAdminPinCritSecInitialized
0x180054e3b  mov     rcx, cs:?g_hthdPreShutdownCleanup@@3PEAXEA; hObject
0x180054e42  test    rcx, rcx
0x180054e45  jz      short loc_180054E58
0x180054e47  call    cs:__imp_CloseHandle
0x180054e4d  mov     cs:?g_hthdPreShutdownCleanup@@3PEAXEA, 0; void * g_hthdPreShutdownCleanup
0x180054e58  add     rsp, 28h
0x180054e5c  retn
```
