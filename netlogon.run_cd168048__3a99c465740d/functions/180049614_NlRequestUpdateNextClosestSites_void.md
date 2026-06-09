# NlRequestUpdateNextClosestSites(void)

- ea: `0x180049614`
- end: `0x1800496ad`
- name: `?NlRequestUpdateNextClosestSites@@YAXXZ`
- size: `153`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18005179c`
- `0x180075b60`

## callees

- `0x180049614`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800496a1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049621`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049621`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18004967d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18004967d`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18004966e`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18004966e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180049657`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180049657`

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
0x180049614  push    rbx
0x180049616  sub     rsp, 20h
0x18004961a  lea     rcx, ?gNlSiteBackgroundLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x180049621  call    cs:__imp_AcquireSRWLockExclusive
0x180049628  nop     dword ptr [rax+rax+00h]
0x18004962d  cmp     cs:?gNlSiteUpdateNextClosestSitesWorkerRunning@@3HA, 0; int gNlSiteUpdateNextClosestSitesWorkerRunning
0x180049634  mov     eax, 1
0x180049639  mov     cs:?gNlSiteUpdateNextClosestSitesRequested@@3HA, eax; int gNlSiteUpdateNextClosestSitesRequested
0x18004963f  jnz     short loc_180049695
0x180049641  lea     r8, ?gNlSiteTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x180049648  mov     cs:?gNlSiteUpdateNextClosestSitesWorkerRunning@@3HA, eax; int gNlSiteUpdateNextClosestSitesWorkerRunning
0x18004964e  xor     edx, edx; pv
0x180049650  lea     rcx, ?NlUpdateNextClosestSitesWorkerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180049657  call    cs:__imp_CreateThreadpoolWork
0x18004965e  nop     dword ptr [rax+rax+00h]
0x180049663  mov     rbx, rax
0x180049666  test    rax, rax
0x180049669  jz      short loc_18004968B
0x18004966b  mov     rcx, rax; pwk
0x18004966e  call    cs:__imp_SubmitThreadpoolWork
0x180049675  nop     dword ptr [rax+rax+00h]
0x18004967a  mov     rcx, rbx; pwk
0x18004967d  call    cs:__imp_CloseThreadpoolWork
0x180049684  nop     dword ptr [rax+rax+00h]
0x180049689  jmp     short loc_180049695
0x18004968b  mov     cs:?gNlSiteUpdateNextClosestSitesWorkerRunning@@3HA, 0; int gNlSiteUpdateNextClosestSitesWorkerRunning
0x180049695  lea     rcx, ?gNlSiteBackgroundLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK gNlSiteBackgroundLock
0x18004969c  add     rsp, 20h
0x1800496a0  pop     rbx
0x1800496a1  jmp     cs:__imp_ReleaseSRWLockExclusive
```
