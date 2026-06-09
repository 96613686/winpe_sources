# NetInfoDeleteLocks

- ea: `0x18009aea0`
- end: `0x18009aeff`
- name: `NetInfoDeleteLocks`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180078efc`

## callees

- `0x18009aea0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009aeab`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009aec7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009aeda`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009aeed`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009aeab`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009aec7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009aeda`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009aeed`

## pseudocode

```c
void NetInfoDeleteLocks()
{
  DeleteCriticalSection(&g_csApiNetInfo);
  if ( g_fVelocityLockGeneralCleanup )
  {
    DeleteCriticalSection(&g_NetInfoCacheLock);
    DeleteCriticalSection(&g_SearchListLock);
    DeleteCriticalSection(&g_NetFailureLock);
  }
}

```

## disassembly

```asm
0x18009aea0  sub     rsp, 28h
0x18009aea4  lea     rcx, g_csApiNetInfo; lpCriticalSection
0x18009aeab  call    cs:__imp_DeleteCriticalSection
0x18009aeb2  nop     dword ptr [rax+rax+00h]
0x18009aeb7  cmp     cs:g_fVelocityLockGeneralCleanup, 0
0x18009aebe  jz      short loc_18009AEF9
0x18009aec0  lea     rcx, g_NetInfoCacheLock; lpCriticalSection
0x18009aec7  call    cs:__imp_DeleteCriticalSection
0x18009aece  nop     dword ptr [rax+rax+00h]
0x18009aed3  lea     rcx, g_SearchListLock; lpCriticalSection
0x18009aeda  call    cs:__imp_DeleteCriticalSection
0x18009aee1  nop     dword ptr [rax+rax+00h]
0x18009aee6  lea     rcx, g_NetFailureLock; lpCriticalSection
0x18009aeed  call    cs:__imp_DeleteCriticalSection
0x18009aef4  nop     dword ptr [rax+rax+00h]
0x18009aef9  add     rsp, 28h
0x18009aefd  retn
```
