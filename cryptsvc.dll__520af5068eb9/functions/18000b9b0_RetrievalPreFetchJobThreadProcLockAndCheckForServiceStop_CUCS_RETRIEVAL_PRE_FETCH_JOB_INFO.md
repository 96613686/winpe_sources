# RetrievalPreFetchJobThreadProcLockAndCheckForServiceStop(_CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO *)

- ea: `0x18000b9b0`
- end: `0x18000b9eb`
- name: `?RetrievalPreFetchJobThreadProcLockAndCheckForServiceStop@@YAHPEAU_CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO@@@Z`
- size: `59`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18000f950`

## callees

- `0x18000b9b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b9de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b9de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b9b9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b9cd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b9b9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b9cd`

## pseudocode

```c
__int64 __fastcall RetrievalPreFetchJobThreadProcLockAndCheckForServiceStop(LPCRITICAL_SECTION lpCriticalSection)
{
  EnterCriticalSection(lpCriticalSection);
  if ( LODWORD(lpCriticalSection[1].DebugInfo) )
  {
    LeaveCriticalSection(lpCriticalSection);
    return 1;
  }
  else
  {
    EnterCriticalSection(&JobsCriticalSection);
    return 0;
  }
}

```

## disassembly

```asm
0x18000b9b0  push    rbx
0x18000b9b2  sub     rsp, 20h
0x18000b9b6  mov     rbx, rcx
0x18000b9b9  call    cs:__imp_EnterCriticalSection
0x18000b9bf  mov     eax, [rbx+28h]
0x18000b9c2  test    eax, eax
0x18000b9c4  jnz     short loc_18000B9DB
0x18000b9c6  lea     rcx, ?JobsCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000b9cd  call    cs:__imp_EnterCriticalSection
0x18000b9d3  xor     eax, eax
0x18000b9d5  add     rsp, 20h
0x18000b9d9  pop     rbx
0x18000b9da  retn
0x18000b9db  mov     rcx, rbx; lpCriticalSection
0x18000b9de  call    cs:__imp_LeaveCriticalSection
0x18000b9e4  mov     eax, 1
0x18000b9e9  jmp     short loc_18000B9D5
```
