# NlSiteAsyncReleaseReference(NLRefcountableObject *)

- ea: `0x180046914`
- end: `0x180046988`
- name: `?NlSiteAsyncReleaseReference@@YAHPEAVNLRefcountableObject@@@Z`
- size: `116`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180046290`
- `0x18004a318`

## callees

- `0x180046914`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180046975`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180046975`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18004692a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18004692a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180046963`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180046963`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18004695a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18004695a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180046949`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180046949`

## pseudocode

```c
__int64 __fastcall NlSiteAsyncReleaseReference(PVOID pv)
{
  unsigned int v2; // edi
  struct _TP_WORK *ThreadpoolWork; // rax
  struct _TP_WORK *v4; // rbx

  v2 = 0;
  AcquireSRWLockShared(&gNlSiteBackgroundLock);
  if ( gNlSiteTPCallbackEnvInitialized )
  {
    ThreadpoolWork = CreateThreadpoolWork(NlSiteAsyncReleaseReferenceWorkerCallback, pv, &gNlSiteTPCallbackEnv);
    v4 = ThreadpoolWork;
    if ( ThreadpoolWork )
    {
      SubmitThreadpoolWork(ThreadpoolWork);
      CloseThreadpoolWork(v4);
      v2 = 1;
    }
  }
  ReleaseSRWLockShared(&gNlSiteBackgroundLock);
  return v2;
}

```

## disassembly

```asm
0x180046914  mov     [rsp+arg_0], rbx
0x180046919  push    rdi
0x18004691a  sub     rsp, 20h
0x18004691e  mov     rbx, rcx
0x180046921  xor     edi, edi
0x180046923  lea     rcx, ?gNlSiteBackgroundLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18004692a  call    cs:__imp_AcquireSRWLockShared
0x180046930  cmp     cs:?gNlSiteTPCallbackEnvInitialized@@3HA, edi; int gNlSiteTPCallbackEnvInitialized
0x180046936  jz      short loc_18004696E
0x180046938  lea     r8, ?gNlSiteTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x18004693f  mov     rdx, rbx; pv
0x180046942  lea     rcx, ?NlSiteAsyncReleaseReferenceWorkerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180046949  call    cs:__imp_CreateThreadpoolWork
0x18004694f  mov     rbx, rax
0x180046952  test    rax, rax
0x180046955  jz      short loc_18004696E
0x180046957  mov     rcx, rax; pwk
0x18004695a  call    cs:__imp_SubmitThreadpoolWork
0x180046960  mov     rcx, rbx; pwk
0x180046963  call    cs:__imp_CloseThreadpoolWork
0x180046969  mov     edi, 1
0x18004696e  lea     rcx, ?gNlSiteBackgroundLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x180046975  call    cs:__imp_ReleaseSRWLockShared
0x18004697b  mov     rbx, [rsp+28h+arg_0]
0x180046980  mov     eax, edi
0x180046982  add     rsp, 20h
0x180046986  pop     rdi
0x180046987  retn
```
