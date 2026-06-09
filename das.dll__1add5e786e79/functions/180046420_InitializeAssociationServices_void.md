# InitializeAssociationServices(void)

- ea: `0x180046420`
- end: `0x180046494`
- name: `?InitializeAssociationServices@@YAJXZ`
- size: `116`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180042f44`

## callees

- `0x180046420`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180046440`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180046440`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180046467`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180046467`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046479`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046479`

## pseudocode

```c
signed int InitializeAssociationServices(void)
{
  signed int result; // eax

  qword_1800A46A8 = (__int64)&qword_1800A46A0;
  qword_1800A46A0 = &qword_1800A46A0;
  InitializeCriticalSection(&ActiveAssociationsList);
  *(_DWORD *)g_cProviderObjectCleanup = 0;
  g_hProviderObjectCleanupCompleteEvent = 0;
  g_hProviderObjectCleanupCompleteEvent = CreateEventW(0, 1, 1, 0);
  if ( g_hProviderObjectCleanupCompleteEvent )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180046420  sub     rsp, 28h
0x180046424  lea     rax, qword_1800A46A0
0x18004642b  lea     rcx, ?ActiveAssociationsList@@3U_DAS_LOCKED_LIST@@A; lpCriticalSection
0x180046432  mov     cs:qword_1800A46A8, rax
0x180046439  mov     cs:qword_1800A46A0, rax
0x180046440  call    cs:__imp_InitializeCriticalSection
0x180046446  xor     r9d, r9d; lpName
0x180046449  mov     cs:?g_cProviderObjectCleanup@@3KC, 0; ulong volatile g_cProviderObjectCleanup
0x180046453  xor     ecx, ecx; lpEventAttributes
0x180046455  mov     cs:?g_hProviderObjectCleanupCompleteEvent@@3PEAXEA, 0; void * g_hProviderObjectCleanupCompleteEvent
0x180046460  lea     edx, [r9+1]; bManualReset
0x180046464  mov     r8d, edx; bInitialState
0x180046467  call    cs:__imp_CreateEventW
0x18004646d  mov     cs:?g_hProviderObjectCleanupCompleteEvent@@3PEAXEA, rax; void * g_hProviderObjectCleanupCompleteEvent
0x180046474  test    rax, rax
0x180046477  jnz     short loc_18004648D
0x180046479  call    cs:__imp_GetLastError
0x18004647f  test    eax, eax
0x180046481  jle     short loc_18004648F
0x180046483  movzx   eax, ax
0x180046486  or      eax, 80070000h
0x18004648b  jmp     short loc_18004648F
0x18004648d  xor     eax, eax
0x18004648f  add     rsp, 28h
0x180046493  retn
```
