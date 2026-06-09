# NlRequestUpdateNextClosestSites(void)

- ea: `0x1800465ac`
- end: `0x180046628`
- name: `?NlRequestUpdateNextClosestSites@@YAXXZ`
- size: `124`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18004e118`
- `0x18007070c`

## callees

- `0x1800465ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180046621`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800465b9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800465b9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180046603`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180046603`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800465fa`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800465fa`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800465e9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800465e9`

## pseudocode

```c
void NlRequestUpdateNextClosestSites(void)
{
  struct _TP_WORK *ThreadpoolWork; // rax
  struct _TP_WORK *v1; // rbx

  AcquireSRWLockExclusive(&gNlSiteBackgroundLock);
  gNlSiteUpdateNextClosestSitesRequested = 1;
  if ( !gNlSiteUpdateNextClosestSitesWorkerRunning )
  {
    gNlSiteUpdateNextClosestSitesWorkerRunning = 1;
    ThreadpoolWork = CreateThreadpoolWork(NlUpdateNextClosestSitesWorkerCallback, 0, &gNlSiteTPCallbackEnv);
    v1 = ThreadpoolWork;
    if ( ThreadpoolWork )
    {
      SubmitThreadpoolWork(ThreadpoolWork);
      CloseThreadpoolWork(v1);
    }
    else
    {
      gNlSiteUpdateNextClosestSitesWorkerRunning = 0;
    }
  }
  ReleaseSRWLockExclusive(&gNlSiteBackgroundLock);
}

```

## disassembly

```asm
0x1800465ac  push    rbx
0x1800465ae  sub     rsp, 20h
0x1800465b2  lea     rcx, ?gNlSiteBackgroundLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x1800465b9  call    cs:__imp_AcquireSRWLockExclusive
0x1800465bf  cmp     cs:?gNlSiteUpdateNextClosestSitesWorkerRunning@@3HA, 0; int gNlSiteUpdateNextClosestSitesWorkerRunning
0x1800465c6  mov     eax, 1
0x1800465cb  mov     cs:?gNlSiteUpdateNextClosestSitesRequested@@3HA, eax; int gNlSiteUpdateNextClosestSitesRequested
0x1800465d1  jnz     short loc_180046615
0x1800465d3  lea     r8, ?gNlSiteTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x1800465da  mov     cs:?gNlSiteUpdateNextClosestSitesWorkerRunning@@3HA, eax; int gNlSiteUpdateNextClosestSitesWorkerRunning
0x1800465e0  xor     edx, edx; pv
0x1800465e2  lea     rcx, ?NlUpdateNextClosestSitesWorkerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800465e9  call    cs:__imp_CreateThreadpoolWork
0x1800465ef  mov     rbx, rax
0x1800465f2  test    rax, rax
0x1800465f5  jz      short loc_18004660B
0x1800465f7  mov     rcx, rax; pwk
0x1800465fa  call    cs:__imp_SubmitThreadpoolWork
0x180046600  mov     rcx, rbx; pwk
0x180046603  call    cs:__imp_CloseThreadpoolWork
0x180046609  jmp     short loc_180046615
0x18004660b  mov     cs:?gNlSiteUpdateNextClosestSitesWorkerRunning@@3HA, 0; int gNlSiteUpdateNextClosestSitesWorkerRunning
0x180046615  lea     rcx, ?gNlSiteBackgroundLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK gNlSiteBackgroundLock
0x18004661c  add     rsp, 20h
0x180046620  pop     rbx
0x180046621  jmp     cs:__imp_ReleaseSRWLockExclusive
```
