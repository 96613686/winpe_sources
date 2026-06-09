# NlSiteAsyncReleaseReference(NLRefcountableObject *)

- ea: `0x1800499ac`
- end: `0x180049a3f`
- name: `?NlSiteAsyncReleaseReference@@YAHPEAVNLRefcountableObject@@@Z`
- size: `147`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800492b0`
- `0x18004d50c`

## callees

- `0x1800499ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180049a25`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180049a25`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800499c2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800499c2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180049a0d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180049a0d`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800499fe`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800499fe`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800499e7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800499e7`

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
0x1800499ac  mov     [rsp+arg_0], rbx
0x1800499b1  push    rdi
0x1800499b2  sub     rsp, 20h
0x1800499b6  mov     rbx, rcx
0x1800499b9  xor     edi, edi
0x1800499bb  lea     rcx, ?gNlSiteBackgroundLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x1800499c2  call    cs:__imp_AcquireSRWLockShared
0x1800499c9  nop     dword ptr [rax+rax+00h]
0x1800499ce  cmp     cs:?gNlSiteTPCallbackEnvInitialized@@3HA, edi; int gNlSiteTPCallbackEnvInitialized
0x1800499d4  jz      short loc_180049A1E
0x1800499d6  lea     r8, ?gNlSiteTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x1800499dd  mov     rdx, rbx; pv
0x1800499e0  lea     rcx, ?NlSiteAsyncReleaseReferenceWorkerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800499e7  call    cs:__imp_CreateThreadpoolWork
0x1800499ee  nop     dword ptr [rax+rax+00h]
0x1800499f3  mov     rbx, rax
0x1800499f6  test    rax, rax
0x1800499f9  jz      short loc_180049A1E
0x1800499fb  mov     rcx, rax; pwk
0x1800499fe  call    cs:__imp_SubmitThreadpoolWork
0x180049a05  nop     dword ptr [rax+rax+00h]
0x180049a0a  mov     rcx, rbx; pwk
0x180049a0d  call    cs:__imp_CloseThreadpoolWork
0x180049a14  nop     dword ptr [rax+rax+00h]
0x180049a19  mov     edi, 1
0x180049a1e  lea     rcx, ?gNlSiteBackgroundLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x180049a25  call    cs:__imp_ReleaseSRWLockShared
0x180049a2c  nop     dword ptr [rax+rax+00h]
0x180049a31  mov     rbx, [rsp+28h+arg_0]
0x180049a36  mov     eax, edi
0x180049a38  add     rsp, 20h
0x180049a3c  pop     rdi
0x180049a3d  retn
```
