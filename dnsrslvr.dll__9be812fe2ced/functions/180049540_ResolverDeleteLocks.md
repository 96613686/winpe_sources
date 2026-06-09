# ResolverDeleteLocks

- ea: `0x180049540`
- end: `0x180049586`
- name: `ResolverDeleteLocks`
- size: `70`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180050ed0`

## callees

- `0x180049540`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004954b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180049561`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004956e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004954b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180049561`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004956e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004957f`

## pseudocode

```c
void ResolverDeleteLocks()
{
  DeleteCriticalSection(&g_csResolverNetInfo);
  if ( !g_fVelocityLockGeneralCleanup )
    DeleteCriticalSection(&g_csGeneralResolver);
  DeleteCriticalSection(&g_csCache);
  DeleteCriticalSection(&g_csNetinfo);
}

```

## disassembly

```asm
0x180049540  sub     rsp, 28h
0x180049544  lea     rcx, g_csResolverNetInfo; lpCriticalSection
0x18004954b  call    cs:__imp_DeleteCriticalSection
0x180049551  cmp     cs:g_fVelocityLockGeneralCleanup, 0
0x180049558  jnz     short loc_180049567
0x18004955a  lea     rcx, g_csGeneralResolver; lpCriticalSection
0x180049561  call    cs:__imp_DeleteCriticalSection
0x180049567  lea     rcx, g_csCache; lpCriticalSection
0x18004956e  call    cs:__imp_DeleteCriticalSection
0x180049574  lea     rcx, g_csNetinfo
0x18004957b  add     rsp, 28h
0x18004957f  jmp     cs:__imp_DeleteCriticalSection
```
