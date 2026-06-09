# NlRequestSitesAndSubnetsCacheRebuild(void)

- ea: `0x18004955c`
- end: `0x18004960b`
- name: `?NlRequestSitesAndSubnetsCacheRebuild@@YAKXZ`
- size: `175`
- prototype: `unsigned int(void)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180049adc`
- `0x180075b60`

## callees

- `0x18004955c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800495f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800495f1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004956f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004956f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800495dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800495dc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800495c8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800495c8`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800495b9`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800495b9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800495a2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800495a2`

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
0x18004955c  mov     [rsp+arg_0], rbx
0x180049561  push    rdi
0x180049562  sub     rsp, 20h
0x180049566  lea     rcx, ?gNlSiteBackgroundLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18004956d  xor     ebx, ebx
0x18004956f  call    cs:__imp_AcquireSRWLockExclusive
0x180049576  nop     dword ptr [rax+rax+00h]
0x18004957b  cmp     cs:?gNlSiteReloadSitesAndSubnetsWorkerRunning@@3HA, ebx; int gNlSiteReloadSitesAndSubnetsWorkerRunning
0x180049581  lea     eax, [rbx+1]
0x180049584  mov     cs:?gNlSiteReloadSitesAndSubnetsRequested@@3HA, eax; int gNlSiteReloadSitesAndSubnetsRequested
0x18004958a  jnz     short loc_1800495EA
0x18004958c  lea     r8, ?gNlSiteTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x180049593  mov     cs:?gNlSiteReloadSitesAndSubnetsWorkerRunning@@3HA, eax; int gNlSiteReloadSitesAndSubnetsWorkerRunning
0x180049599  xor     edx, edx; pv
0x18004959b  lea     rcx, ?NlRebuildSitesAndSubnetsCacheWorkerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800495a2  call    cs:__imp_CreateThreadpoolWork
0x1800495a9  nop     dword ptr [rax+rax+00h]
0x1800495ae  mov     rdi, rax
0x1800495b1  test    rax, rax
0x1800495b4  jz      short loc_1800495D6
0x1800495b6  mov     rcx, rax; pwk
0x1800495b9  call    cs:__imp_SubmitThreadpoolWork
0x1800495c0  nop     dword ptr [rax+rax+00h]
0x1800495c5  mov     rcx, rdi; pwk
0x1800495c8  call    cs:__imp_CloseThreadpoolWork
0x1800495cf  nop     dword ptr [rax+rax+00h]
0x1800495d4  jmp     short loc_1800495EA
0x1800495d6  mov     cs:?gNlSiteReloadSitesAndSubnetsWorkerRunning@@3HA, ebx; int gNlSiteReloadSitesAndSubnetsWorkerRunning
0x1800495dc  call    cs:__imp_GetLastError
0x1800495e3  nop     dword ptr [rax+rax+00h]
0x1800495e8  mov     ebx, eax
0x1800495ea  lea     rcx, ?gNlSiteBackgroundLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x1800495f1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800495f8  nop     dword ptr [rax+rax+00h]
0x1800495fd  mov     eax, ebx
0x1800495ff  mov     rbx, [rsp+28h+arg_0]
0x180049604  add     rsp, 20h
0x180049608  pop     rdi
0x180049609  retn
```
