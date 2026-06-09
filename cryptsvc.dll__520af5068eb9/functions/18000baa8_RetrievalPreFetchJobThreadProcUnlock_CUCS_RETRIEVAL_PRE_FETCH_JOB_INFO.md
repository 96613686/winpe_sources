# RetrievalPreFetchJobThreadProcUnlock(_CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO *)

- ea: `0x18000baa8`
- end: `0x18000bacd`
- name: `?RetrievalPreFetchJobThreadProcUnlock@@YAXPEAU_CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO@@@Z`
- size: `37`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18000f950`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bab8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bab8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bac6`

## pseudocode

```c
void __fastcall RetrievalPreFetchJobThreadProcUnlock(struct _RTL_CRITICAL_SECTION *a1)
{
  LeaveCriticalSection(&JobsCriticalSection);
  LeaveCriticalSection(a1);
}

```

## disassembly

```asm
0x18000baa8  push    rbx
0x18000baaa  sub     rsp, 20h
0x18000baae  mov     rbx, rcx
0x18000bab1  lea     rcx, ?JobsCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000bab8  call    cs:__imp_LeaveCriticalSection
0x18000babe  mov     rcx, rbx
0x18000bac1  add     rsp, 20h
0x18000bac5  pop     rbx
0x18000bac6  jmp     cs:__imp_LeaveCriticalSection
```
