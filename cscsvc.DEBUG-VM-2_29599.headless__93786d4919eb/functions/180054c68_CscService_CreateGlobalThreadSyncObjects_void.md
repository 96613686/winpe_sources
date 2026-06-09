# CscService_CreateGlobalThreadSyncObjects(void)

- ea: `0x180054c68`
- end: `0x180054d78`
- name: `?CscService_CreateGlobalThreadSyncObjects@@YAJXZ`
- size: `272`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180054340`

## callees

- `0x18002f10c`
- `0x180054c68`
- `0x180054d80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180054cfd`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180054d23`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180054d49`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180054cfd`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180054d23`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180054d49`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180054c81`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180054cac`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180054cd7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180054c81`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180054cac`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180054cd7`

## pseudocode

```c
__int64 CscService_CreateGlobalThreadSyncObjects(void)
{
  int Error; // ebx

  Error = 0;
  g_hevtDone = CreateEventW(0, 1, 0, 0);
  if ( !g_hevtDone )
  {
    Error = ResultFromLastError();
    if ( Error < 0 )
      goto LABEL_16;
  }
  g_hevtStop = CreateEventW(0, 1, 0, 0);
  if ( !g_hevtStop )
  {
    Error = ResultFromLastError();
    if ( Error < 0 )
      goto LABEL_16;
  }
  g_hevtReady = CreateEventW(0, 1, 0, 0);
  if ( !g_hevtReady )
  {
    Error = ResultFromLastError();
    if ( Error < 0 )
      goto LABEL_16;
  }
  if ( InitializeCriticalSectionAndSpinCount(&g_csAdminPin, 0) )
  {
    g_bAdminPinCritSecInitialized = 1;
  }
  else
  {
    Error = ResultFromLastError();
    if ( Error < 0 )
      goto LABEL_16;
  }
  if ( InitializeCriticalSectionAndSpinCount(&g_csDone, 0) )
  {
    g_bDoneCritSecInitialized = 1;
  }
  else
  {
    Error = ResultFromLastError();
    if ( Error < 0 )
      goto LABEL_16;
  }
  if ( !InitializeCriticalSectionAndSpinCount(&g_csPrefetchCloseHandle, 0) )
  {
    Error = ResultFromLastError();
    if ( Error >= 0 )
      return (unsigned int)Error;
LABEL_16:
    CscService_DestroyGlobalThreadSyncObjects();
    return (unsigned int)Error;
  }
  g_bPrefetchCloseHandleCritSecInitialized = 1;
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180054c68  mov     [rsp+arg_0], rbx
0x180054c6d  push    rdi
0x180054c6e  sub     rsp, 20h
0x180054c72  xor     ebx, ebx
0x180054c74  xor     r9d, r9d; lpName
0x180054c77  xor     r8d, r8d; bInitialState
0x180054c7a  xor     ecx, ecx; lpEventAttributes
0x180054c7c  lea     edi, [rbx+1]
0x180054c7f  mov     edx, edi; bManualReset
0x180054c81  call    cs:__imp_CreateEventW
0x180054c87  mov     cs:?g_hevtDone@@3PEAXEA, rax; void * g_hevtDone
0x180054c8e  test    rax, rax
0x180054c91  jnz     short loc_180054CA2
0x180054c93  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180054c98  mov     ebx, eax
0x180054c9a  test    eax, eax
0x180054c9c  js      loc_180054D66
0x180054ca2  xor     r9d, r9d; lpName
0x180054ca5  xor     r8d, r8d; bInitialState
0x180054ca8  mov     edx, edi; bManualReset
0x180054caa  xor     ecx, ecx; lpEventAttributes
0x180054cac  call    cs:__imp_CreateEventW
0x180054cb2  mov     cs:?g_hevtStop@@3PEAXEA, rax; void * g_hevtStop
0x180054cb9  test    rax, rax
0x180054cbc  jnz     short loc_180054CCD
0x180054cbe  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180054cc3  mov     ebx, eax
0x180054cc5  test    eax, eax
0x180054cc7  js      loc_180054D66
0x180054ccd  xor     r9d, r9d; lpName
0x180054cd0  xor     r8d, r8d; bInitialState
0x180054cd3  mov     edx, edi; bManualReset
0x180054cd5  xor     ecx, ecx; lpEventAttributes
0x180054cd7  call    cs:__imp_CreateEventW
0x180054cdd  mov     cs:?g_hevtReady@@3PEAXEA, rax; void * g_hevtReady
0x180054ce4  test    rax, rax
0x180054ce7  jnz     short loc_180054CF4
0x180054ce9  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180054cee  mov     ebx, eax
0x180054cf0  test    eax, eax
0x180054cf2  js      short loc_180054D66
0x180054cf4  xor     edx, edx; dwSpinCount
0x180054cf6  lea     rcx, ?g_csAdminPin@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180054cfd  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180054d03  test    eax, eax
0x180054d05  jz      short loc_180054D0F
0x180054d07  mov     cs:?g_bAdminPinCritSecInitialized@@3HA, edi; int g_bAdminPinCritSecInitialized
0x180054d0d  jmp     short loc_180054D1A
0x180054d0f  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180054d14  mov     ebx, eax
0x180054d16  test    eax, eax
0x180054d18  js      short loc_180054D66
0x180054d1a  xor     edx, edx; dwSpinCount
0x180054d1c  lea     rcx, ?g_csDone@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180054d23  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180054d29  test    eax, eax
0x180054d2b  jz      short loc_180054D35
0x180054d2d  mov     cs:?g_bDoneCritSecInitialized@@3HA, edi; int g_bDoneCritSecInitialized
0x180054d33  jmp     short loc_180054D40
0x180054d35  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180054d3a  mov     ebx, eax
0x180054d3c  test    eax, eax
0x180054d3e  js      short loc_180054D66
0x180054d40  xor     edx, edx; dwSpinCount
0x180054d42  lea     rcx, ?g_csPrefetchCloseHandle@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180054d49  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180054d4f  test    eax, eax
0x180054d51  jz      short loc_180054D5B
0x180054d53  mov     cs:?g_bPrefetchCloseHandleCritSecInitialized@@3HA, edi; int g_bPrefetchCloseHandleCritSecInitialized
0x180054d59  jmp     short loc_180054D6B
0x180054d5b  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180054d60  mov     ebx, eax
0x180054d62  test    eax, eax
0x180054d64  jns     short loc_180054D6B
0x180054d66  call    ?CscService_DestroyGlobalThreadSyncObjects@@YAXXZ; CscService_DestroyGlobalThreadSyncObjects(void)
0x180054d6b  mov     eax, ebx
0x180054d6d  mov     rbx, [rsp+28h+arg_0]
0x180054d72  add     rsp, 20h
0x180054d76  pop     rdi
0x180054d77  retn
```
