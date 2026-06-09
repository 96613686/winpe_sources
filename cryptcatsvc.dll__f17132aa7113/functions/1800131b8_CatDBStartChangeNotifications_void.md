# _CatDBStartChangeNotifications(void)

- ea: `0x1800131b8`
- end: `0x180013319`
- name: `?_CatDBStartChangeNotifications@@YAHXZ`
- size: `353`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000ad54`

## callees

- `0x18000a59c`
- `0x18000c7e8`
- `0x180012ef4`
- `0x1800131b8`
- `0x180013320`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001325a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001325a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800131da`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800131da`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800132d1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800132d1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180013280`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180013280`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800132a6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800132a6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180013232`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180013232`

## pseudocode

```c
__int64 _CatDBStartChangeNotifications(void)
{
  unsigned int v0; // ebx
  unsigned int v1; // edx
  unsigned __int16 *v2; // rcx
  unsigned int v3; // r8d
  struct _TP_WAIT *ThreadpoolWait; // rax
  DWORD dwFlagsAndAttributes; // [rsp+28h] [rbp-20h]

  qword_1800326C8 = (__int64)&g_IgnoreList;
  g_IgnoreList.Flink = &g_IgnoreList;
  InitializeCriticalSection(&g_IgnoreListCS);
  g_CatrootChangesSyncInFlight = 0;
  g_CatalogChangesShuttingDown = 0;
  memset_0(&g_CatrootChangesWaitContext, 0, 0x1028u);
  v0 = 1;
  g_CatrootChangesWaitContext = CreateFileW(g_pwszCatalogFileBaseDirectory, 1u, 7u, 0, 3u, 0x42000000u, 0);
  if ( g_CatrootChangesWaitContext == (HANDLE)-1LL )
  {
    v3 = 749;
  }
  else
  {
    hObject = CreateEventW(0, 0, 0, 0);
    if ( hObject )
    {
      g_CatrootSyncWork = CreateThreadpoolWork(CatrootSyncWorkCallback, 0, 0);
      if ( g_CatrootSyncWork )
      {
        g_DrainIgnoreListTimer = CreateThreadpoolTimer(DrainIgnoreListTimerCallback, 0, 0);
        if ( g_DrainIgnoreListTimer )
        {
          ThreadpoolWait = CreateThreadpoolWait(WaitForCatrootChangesCallback, &g_CatrootChangesWaitContext, 0);
          g_CatrootChangesWait = ThreadpoolWait;
          if ( ThreadpoolWait )
          {
            SubmitWaitForCatrootChanges(ThreadpoolWait);
            return v0;
          }
          v3 = 773;
        }
        else
        {
          v3 = 767;
        }
      }
      else
      {
        v3 = 761;
      }
    }
    else
    {
      v3 = 755;
    }
  }
  ErrLog_LogError(v2, v1, v3, 0, 0, dwFlagsAndAttributes);
  _CatDBStopChangeNotifications();
  return 0;
}

```

## disassembly

```asm
0x1800131b8  push    rbx
0x1800131ba  sub     rsp, 40h
0x1800131be  lea     rax, ?g_IgnoreList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_IgnoreList
0x1800131c5  lea     rcx, ?g_IgnoreListCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800131cc  mov     cs:qword_1800326C8, rax
0x1800131d3  mov     cs:?g_IgnoreList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY g_IgnoreList
0x1800131da  call    cs:__imp_InitializeCriticalSection
0x1800131e0  xor     edx, edx; Val
0x1800131e2  mov     cs:?g_CatrootChangesSyncInFlight@@3JA, 0; long g_CatrootChangesSyncInFlight
0x1800131ec  mov     r8d, 1028h; Size
0x1800131f2  mov     cs:?g_CatalogChangesShuttingDown@@3EA, 0; uchar g_CatalogChangesShuttingDown
0x1800131f9  lea     rcx, ?g_CatrootChangesWaitContext@@3UCATDB_CHANGES_WAIT_CONTEXT@@A; void *
0x180013200  call    memset_0
0x180013205  mov     rcx, cs:?g_pwszCatalogFileBaseDirectory@@3PEAGEA; lpFileName
0x18001320c  xor     r9d, r9d; lpSecurityAttributes
0x18001320f  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180013218  mov     [rsp+48h+dwFlagsAndAttributes], 42000000h; int
0x180013220  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180013228  lea     ebx, [r9+1]
0x18001322c  mov     edx, ebx; dwDesiredAccess
0x18001322e  lea     r8d, [r9+7]; dwShareMode
0x180013232  call    cs:__imp_CreateFileW
0x180013238  mov     cs:?g_CatrootChangesWaitContext@@3UCATDB_CHANGES_WAIT_CONTEXT@@A, rax; CATDB_CHANGES_WAIT_CONTEXT g_CatrootChangesWaitContext
0x18001323f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180013243  jnz     short loc_180013250
0x180013245  mov     r8d, 2EDh
0x18001324b  jmp     loc_1800132E9
0x180013250  xor     r9d, r9d; lpName
0x180013253  xor     r8d, r8d; bInitialState
0x180013256  xor     edx, edx; bManualReset
0x180013258  xor     ecx, ecx; lpEventAttributes
0x18001325a  call    cs:__imp_CreateEventW
0x180013260  mov     cs:hObject, rax
0x180013267  test    rax, rax
0x18001326a  jnz     short loc_180013274
0x18001326c  mov     r8d, 2F3h
0x180013272  jmp     short loc_1800132E9
0x180013274  xor     r8d, r8d; pcbe
0x180013277  lea     rcx, CatrootSyncWorkCallback; pfnwk
0x18001327e  xor     edx, edx; pv
0x180013280  call    cs:__imp_CreateThreadpoolWork
0x180013286  mov     cs:?g_CatrootSyncWork@@3PEAU_TP_WORK@@EA, rax; _TP_WORK * g_CatrootSyncWork
0x18001328d  test    rax, rax
0x180013290  jnz     short loc_18001329A
0x180013292  mov     r8d, 2F9h
0x180013298  jmp     short loc_1800132E9
0x18001329a  xor     r8d, r8d; pcbe
0x18001329d  lea     rcx, DrainIgnoreListTimerCallback; pfnti
0x1800132a4  xor     edx, edx; pv
0x1800132a6  call    cs:__imp_CreateThreadpoolTimer
0x1800132ac  mov     cs:?g_DrainIgnoreListTimer@@3PEAU_TP_TIMER@@EA, rax; _TP_TIMER * g_DrainIgnoreListTimer
0x1800132b3  test    rax, rax
0x1800132b6  jnz     short loc_1800132C0
0x1800132b8  mov     r8d, 2FFh
0x1800132be  jmp     short loc_1800132E9
0x1800132c0  xor     r8d, r8d; pcbe
0x1800132c3  lea     rdx, ?g_CatrootChangesWaitContext@@3UCATDB_CHANGES_WAIT_CONTEXT@@A; pv
0x1800132ca  lea     rcx, WaitForCatrootChangesCallback; pfnwa
0x1800132d1  call    cs:__imp_CreateThreadpoolWait
0x1800132d7  mov     cs:?g_CatrootChangesWait@@3PEAU_TP_WAIT@@EA, rax; _TP_WAIT * g_CatrootChangesWait
0x1800132de  test    rax, rax
0x1800132e1  jnz     short loc_180013302
0x1800132e3  mov     r8d, 305h; unsigned int
0x1800132e9  xor     r9d, r9d; unsigned int
0x1800132ec  mov     [rsp+48h+dwCreationDisposition], 0; int
0x1800132f4  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x1800132f9  call    ?_CatDBStopChangeNotifications@@YAXXZ; _CatDBStopChangeNotifications(void)
0x1800132fe  xor     ebx, ebx
0x180013300  jmp     short loc_180013311
0x180013302  lea     rdx, ?g_CatrootChangesWaitContext@@3UCATDB_CHANGES_WAIT_CONTEXT@@A; CATDB_CHANGES_WAIT_CONTEXT g_CatrootChangesWaitContext
0x180013309  mov     rcx, rax; pwa
0x18001330c  call    SubmitWaitForCatrootChanges
0x180013311  mov     eax, ebx
0x180013313  add     rsp, 40h
0x180013317  pop     rbx
0x180013318  retn
```
