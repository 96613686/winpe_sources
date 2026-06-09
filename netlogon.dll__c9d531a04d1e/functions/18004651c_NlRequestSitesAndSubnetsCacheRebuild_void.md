# NlRequestSitesAndSubnetsCacheRebuild(void)

- ea: `0x18004651c`
- end: `0x1800465a6`
- name: `?NlRequestSitesAndSubnetsCacheRebuild@@YAKXZ`
- size: `138`
- prototype: `unsigned int(void)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180046a0c`
- `0x18007070c`

## callees

- `0x18004651c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180046593`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180046593`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004652f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004652f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046584`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046584`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180046576`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180046576`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18004656d`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18004656d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18004655c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18004655c`

## pseudocode

```c
__int64 NlRequestSitesAndSubnetsCacheRebuild(void)
{
  DWORD LastError; // ebx
  struct _TP_WORK *ThreadpoolWork; // rax
  struct _TP_WORK *v2; // rdi

  LastError = 0;
  AcquireSRWLockExclusive(&gNlSiteBackgroundLock);
  gNlSiteReloadSitesAndSubnetsRequested = 1;
  if ( !gNlSiteReloadSitesAndSubnetsWorkerRunning )
  {
    gNlSiteReloadSitesAndSubnetsWorkerRunning = 1;
    ThreadpoolWork = CreateThreadpoolWork(NlRebuildSitesAndSubnetsCacheWorkerCallback, 0, &gNlSiteTPCallbackEnv);
    v2 = ThreadpoolWork;
    if ( ThreadpoolWork )
    {
      SubmitThreadpoolWork(ThreadpoolWork);
      CloseThreadpoolWork(v2);
    }
    else
    {
      gNlSiteReloadSitesAndSubnetsWorkerRunning = 0;
      LastError = GetLastError();
    }
  }
  ReleaseSRWLockExclusive(&gNlSiteBackgroundLock);
  return LastError;
}

```

## disassembly

```asm
0x18004651c  mov     [rsp+arg_0], rbx
0x180046521  push    rdi
0x180046522  sub     rsp, 20h
0x180046526  lea     rcx, ?gNlSiteBackgroundLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18004652d  xor     ebx, ebx
0x18004652f  call    cs:__imp_AcquireSRWLockExclusive
0x180046535  cmp     cs:?gNlSiteReloadSitesAndSubnetsWorkerRunning@@3HA, ebx; int gNlSiteReloadSitesAndSubnetsWorkerRunning
0x18004653b  lea     eax, [rbx+1]
0x18004653e  mov     cs:?gNlSiteReloadSitesAndSubnetsRequested@@3HA, eax; int gNlSiteReloadSitesAndSubnetsRequested
0x180046544  jnz     short loc_18004658C
0x180046546  lea     r8, ?gNlSiteTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x18004654d  mov     cs:?gNlSiteReloadSitesAndSubnetsWorkerRunning@@3HA, eax; int gNlSiteReloadSitesAndSubnetsWorkerRunning
0x180046553  xor     edx, edx; pv
0x180046555  lea     rcx, ?NlRebuildSitesAndSubnetsCacheWorkerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18004655c  call    cs:__imp_CreateThreadpoolWork
0x180046562  mov     rdi, rax
0x180046565  test    rax, rax
0x180046568  jz      short loc_18004657E
0x18004656a  mov     rcx, rax; pwk
0x18004656d  call    cs:__imp_SubmitThreadpoolWork
0x180046573  mov     rcx, rdi; pwk
0x180046576  call    cs:__imp_CloseThreadpoolWork
0x18004657c  jmp     short loc_18004658C
0x18004657e  mov     cs:?gNlSiteReloadSitesAndSubnetsWorkerRunning@@3HA, ebx; int gNlSiteReloadSitesAndSubnetsWorkerRunning
0x180046584  call    cs:__imp_GetLastError
0x18004658a  mov     ebx, eax
0x18004658c  lea     rcx, ?gNlSiteBackgroundLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x180046593  call    cs:__imp_ReleaseSRWLockExclusive
0x180046599  mov     eax, ebx
0x18004659b  mov     rbx, [rsp+28h+arg_0]
0x1800465a0  add     rsp, 20h
0x1800465a4  pop     rdi
0x1800465a5  retn
```
