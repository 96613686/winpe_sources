# ProcessToBeRunServiceStopJob

- ea: `0x18000d134`
- end: `0x18000d255`
- name: `ProcessToBeRunServiceStopJob`
- size: `289`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180005460`

## callees

- `0x1800041bc`
- `0x1800088f0`
- `0x18000a660`
- `0x18000d134`
- `0x18000d4c0`
- `0x18000f924`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d17d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d1a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d1c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d1fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d203`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d17d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d1a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d1c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d1fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d203`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d14a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d1b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d1d9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d14a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d1b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d1d9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000d246`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000d246`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d22c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d22c`

## pseudocode

```c
void __fastcall ProcessToBeRunServiceStopJob(__int64 a1)
{
  _QWORD *v2; // rbx
  _DWORD *v3; // rdi
  HLOCAL v4; // rbx
  struct _RTL_CRITICAL_SECTION *v5; // rcx
  void *v6; // rcx

  EnterCriticalSection(&JobsCriticalSection);
  v2 = pToBeRunJobHead;
  while ( v2 )
  {
    v3 = v2;
    v2 = (_QWORD *)*v2;
    if ( v3[6] == 1 )
    {
      RemoveToBeRunJob(v3);
      FreeTriggerJob(v3);
    }
  }
  LeaveCriticalSection(&JobsCriticalSection);
  while ( 1 )
  {
    EnterCriticalSection(&JobsCriticalSection);
    v4 = pPendingLogoffExitJobHead;
    if ( !pPendingLogoffExitJobHead )
      break;
    *((_DWORD *)pPendingLogoffExitJobHead + 16) = 1;
    RemoveFromLinkList(&pPendingLogoffExitJobHead, v4, 0);
    LeaveCriticalSection(&JobsCriticalSection);
    ProcessToBeRunLogoffExitJob(v4);
  }
  LeaveCriticalSection(&JobsCriticalSection);
  if ( pRetrievalPreFetchJobInfo )
  {
    EnterCriticalSection(pRetrievalPreFetchJobInfo);
    v5 = pRetrievalPreFetchJobInfo;
    if ( HIDWORD(pRetrievalPreFetchJobInfo[1].DebugInfo) )
    {
      LODWORD(pRetrievalPreFetchJobInfo[1].DebugInfo) = 1;
      LeaveCriticalSection(v5);
    }
    else
    {
      LeaveCriticalSection(pRetrievalPreFetchJobInfo);
      FreeRetrievalPreFetchJobInfo(pRetrievalPreFetchJobInfo);
    }
    pRetrievalPreFetchJobInfo = 0;
  }
  if ( hToBeRunJobEvent )
  {
    CloseHandle(hToBeRunJobEvent);
    hToBeRunJobEvent = 0;
  }
  v6 = *(void **)(a1 + 32);
  if ( v6 )
    SetEvent(v6);
}

```

## disassembly

```asm
0x18000d134  push    rbx
0x18000d136  push    rbp
0x18000d137  push    rsi
0x18000d138  push    rdi
0x18000d139  sub     rsp, 28h
0x18000d13d  mov     rsi, rcx
0x18000d140  lea     rbp, ?JobsCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION JobsCriticalSection
0x18000d147  mov     rcx, rbp; lpCriticalSection
0x18000d14a  call    cs:__imp_EnterCriticalSection
0x18000d150  mov     rbx, cs:?pToBeRunJobHead@@3PEAU_CUCS_JOB_HEADER@@EA; _CUCS_JOB_HEADER * pToBeRunJobHead
0x18000d157  jmp     short loc_18000D175
0x18000d159  mov     rdi, rbx
0x18000d15c  mov     rbx, [rbx]
0x18000d15f  cmp     dword ptr [rdi+18h], 1
0x18000d163  jnz     short loc_18000D175
0x18000d165  mov     rcx, rdi
0x18000d168  call    RemoveToBeRunJob
0x18000d16d  mov     rcx, rdi; hMem
0x18000d170  call    FreeTriggerJob
0x18000d175  test    rbx, rbx
0x18000d178  jnz     short loc_18000D159
0x18000d17a  mov     rcx, rbp; lpCriticalSection
0x18000d17d  call    cs:__imp_LeaveCriticalSection
0x18000d183  jmp     short loc_18000D1AF
0x18000d185  xor     r8d, r8d
0x18000d188  mov     dword ptr [rbx+40h], 1
0x18000d18f  mov     rdx, rbx
0x18000d192  lea     rcx, ?pPendingLogoffExitJobHead@@3PEAU_CUCS_LOGOFF_EXIT_JOB_ENTRY@@EA; _CUCS_LOGOFF_EXIT_JOB_ENTRY * pPendingLogoffExitJobHead
0x18000d199  call    RemoveFromLinkList
0x18000d19e  mov     rcx, rbp; lpCriticalSection
0x18000d1a1  call    cs:__imp_LeaveCriticalSection
0x18000d1a7  mov     rcx, rbx; hMem
0x18000d1aa  call    ProcessToBeRunLogoffExitJob
0x18000d1af  mov     rcx, rbp; lpCriticalSection
0x18000d1b2  call    cs:__imp_EnterCriticalSection
0x18000d1b8  mov     rbx, cs:?pPendingLogoffExitJobHead@@3PEAU_CUCS_LOGOFF_EXIT_JOB_ENTRY@@EA; _CUCS_LOGOFF_EXIT_JOB_ENTRY * pPendingLogoffExitJobHead
0x18000d1bf  test    rbx, rbx
0x18000d1c2  jnz     short loc_18000D185
0x18000d1c4  mov     rcx, rbp; lpCriticalSection
0x18000d1c7  call    cs:__imp_LeaveCriticalSection
0x18000d1cd  mov     rcx, cs:?pRetrievalPreFetchJobInfo@@3PEAU_CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO@@EA; lpCriticalSection
0x18000d1d4  test    rcx, rcx
0x18000d1d7  jz      short loc_18000D220
0x18000d1d9  call    cs:__imp_EnterCriticalSection
0x18000d1df  mov     rax, cs:?pRetrievalPreFetchJobInfo@@3PEAU_CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO@@EA; _CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO * pRetrievalPreFetchJobInfo
0x18000d1e6  mov     ecx, [rax+2Ch]
0x18000d1e9  test    ecx, ecx
0x18000d1eb  mov     rcx, cs:?pRetrievalPreFetchJobInfo@@3PEAU_CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO@@EA; lpCriticalSection
0x18000d1f2  jz      short loc_18000D203
0x18000d1f4  mov     dword ptr [rcx+28h], 1
0x18000d1fb  call    cs:__imp_LeaveCriticalSection
0x18000d201  jmp     short loc_18000D215
0x18000d203  call    cs:__imp_LeaveCriticalSection
0x18000d209  mov     rcx, cs:?pRetrievalPreFetchJobInfo@@3PEAU_CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO@@EA; hMem
0x18000d210  call    ?FreeRetrievalPreFetchJobInfo@@YAXPEAU_CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO@@@Z; FreeRetrievalPreFetchJobInfo(_CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO *)
0x18000d215  mov     cs:?pRetrievalPreFetchJobInfo@@3PEAU_CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO@@EA, 0; _CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO * pRetrievalPreFetchJobInfo
0x18000d220  mov     rcx, cs:?hToBeRunJobEvent@@3PEAXEA; hObject
0x18000d227  test    rcx, rcx
0x18000d22a  jz      short loc_18000D23D
0x18000d22c  call    cs:__imp_CloseHandle
0x18000d232  mov     cs:?hToBeRunJobEvent@@3PEAXEA, 0; void * hToBeRunJobEvent
0x18000d23d  mov     rcx, [rsi+20h]; hEvent
0x18000d241  test    rcx, rcx
0x18000d244  jz      short loc_18000D24C
0x18000d246  call    cs:__imp_SetEvent
0x18000d24c  add     rsp, 28h
0x18000d250  pop     rdi
0x18000d251  pop     rsi
0x18000d252  pop     rbp
0x18000d253  pop     rbx
0x18000d254  retn
```
