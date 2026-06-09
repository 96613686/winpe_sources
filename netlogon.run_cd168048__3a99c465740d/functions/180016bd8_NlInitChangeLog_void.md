# NlInitChangeLog(void)

- ea: `0x180016bd8`
- end: `0x180016db1`
- name: `?NlInitChangeLog@@YAJXZ`
- size: `473`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x180079874`

## callees

- `0x180007518`
- `0x18000d7a0`
- `0x180016bd8`
- `0x18008ac1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016d00`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016d4d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016d00`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016d4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016d18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016d65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016d18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016d65`
- `ntdll!RtlInitializeCriticalSection` at `0x180016bf1`
- `ntdll!RtlInitializeCriticalSection` at `0x180016c04`
- `ntdll!RtlInitializeCriticalSection` at `0x180016c27`
- `ntdll!RtlInitializeCriticalSection` at `0x180016bf1`
- `ntdll!RtlInitializeCriticalSection` at `0x180016c04`
- `ntdll!RtlInitializeCriticalSection` at `0x180016c27`
- `ntdll!RtlGetNtProductType` at `0x180016d7f`
- `ntdll!RtlGetNtProductType` at `0x180016d7f`

## string_xrefs

- `0x180016cdb`: `Cannot NetpEventlogOpen\n`
- `0x180016d24`: `Cannot create ChangeLog Event %lu\n`
- `0x180016d71`: `Cannot create TrustInfoUpToDate Event %lu\n`

## pseudocode

```c
__int64 NlInitChangeLog(void)
{
  __int64 v0; // rdi
  _NT_PRODUCT_TYPE v1; // ebx
  DWORD LastError; // eax
  unsigned __int16 *v4; // rdx
  DWORD v5; // ebx
  _NT_PRODUCT_TYPE ProductType; // [rsp+30h] [rbp+8h] BYREF

  ProductType = 0;
  RtlInitializeCriticalSection(&NlGlobalLogFileCritSect);
  RtlInitializeCriticalSection(&NlGlobalChangeLogCritSect);
  v0 = 0;
  v1 = NtProductWinNt;
  do
    RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)(&NlGlobalSecPkgCritSect + 6 * v0++));
  while ( v0 != 16 );
  NlGlobalParameters = -1;
  qword_1800F7A38 = (__int64)&NlGlobalChangeLogNotifications;
  NlGlobalChangeLogNotifications.Flink = &NlGlobalChangeLogNotifications;
  NlGlobalLogFile = (HANDLE)-1LL;
  dword_1800F8104 = 20000000;
  NlGlobalLogFileOutputBuffer = 0;
  NlGlobalLogFileUtf8Buffer = 0;
  NlGlobalChangeLogServiceBits = 0;
  NlGlobalChangeLogWorkerThreadHandle = 0;
  NlGlobalChangeLogNotifyBrowser = 0;
  NlGlobalChangeLogWorkerIsRunning = 0;
  NlGlobalChangeLogDllUnloaded = 1;
  NlGlobalChangeLogNetlogonState = 0;
  NlGlobalChangeLogEvent = 0;
  NlGlobalEventlogHandle = (LPCRITICAL_SECTION)NetpEventlogOpen();
  if ( !NlGlobalEventlogHandle )
  {
    NlPrintRoutine(0x100u, L"Cannot NetpEventlogOpen\n");
    return 3221225495LL;
  }
  NlGlobalChangeLogEvent = CreateEventW(0, 0, 0, 0);
  if ( !NlGlobalChangeLogEvent )
  {
    LastError = GetLastError();
    v4 = L"Cannot create ChangeLog Event %lu\n";
LABEL_7:
    v5 = LastError;
    NlPrintRoutine(0x100u, v4, LastError);
    return NetpApiStatusToNtStatus(v5);
  }
  NlGlobalTrustInfoUpToDateEvent = CreateEventW(0, 1, 1, 0);
  if ( !NlGlobalTrustInfoUpToDateEvent )
  {
    LastError = GetLastError();
    v4 = L"Cannot create TrustInfoUpToDate Event %lu\n";
    goto LABEL_7;
  }
  if ( RtlGetNtProductType(&ProductType) )
    v1 = ProductType;
  NlGlobalChangeLogRole = 3 - (v1 != NtProductLanManNt);
  return 0;
}

```

## disassembly

```asm
0x180016bd8  mov     [rsp+arg_8], rbx
0x180016bdd  push    rdi
0x180016bde  sub     rsp, 20h
0x180016be2  lea     rcx, ?NlGlobalLogFileCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180016be9  mov     [rsp+28h+ProductType], 0
0x180016bf1  call    cs:__imp_RtlInitializeCriticalSection
0x180016bf8  nop     dword ptr [rax+rax+00h]
0x180016bfd  lea     rcx, ?NlGlobalChangeLogCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180016c04  call    cs:__imp_RtlInitializeCriticalSection
0x180016c0b  nop     dword ptr [rax+rax+00h]
0x180016c10  xor     edi, edi
0x180016c12  lea     ebx, [rdi+1]
0x180016c15  lea     rax, ?NlGlobalSecPkgCritSect@@3PAU_SAFE_CRITICAL_SECTION@@A; _SAFE_CRITICAL_SECTION near * NlGlobalSecPkgCritSect
0x180016c1c  lea     rcx, [rdi+rdi*2]
0x180016c20  shl     rcx, 4
0x180016c24  add     rcx, rax; CriticalSection
0x180016c27  call    cs:__imp_RtlInitializeCriticalSection
0x180016c2e  nop     dword ptr [rax+rax+00h]
0x180016c33  add     rdi, rbx
0x180016c36  cmp     rdi, 10h
0x180016c3a  jnz     short loc_180016C15
0x180016c3c  lea     rax, ?NlGlobalChangeLogNotifications@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalChangeLogNotifications
0x180016c43  mov     cs:?NlGlobalParameters@@3U_NETLOGON_PARAMETERS@@A, 0FFFFFFFFh; _NETLOGON_PARAMETERS NlGlobalParameters
0x180016c4d  mov     cs:qword_1800F7A38, rax
0x180016c54  mov     cs:?NlGlobalChangeLogNotifications@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY NlGlobalChangeLogNotifications
0x180016c5b  mov     cs:?NlGlobalLogFile@@3PEAXEA, 0FFFFFFFFFFFFFFFFh; void * NlGlobalLogFile
0x180016c66  mov     cs:dword_1800F8104, 1312D00h
0x180016c70  mov     cs:?NlGlobalLogFileOutputBuffer@@3PEAGEA, 0; ushort * NlGlobalLogFileOutputBuffer
0x180016c7b  mov     cs:?NlGlobalLogFileUtf8Buffer@@3PEAEEA, 0; uchar * NlGlobalLogFileUtf8Buffer
0x180016c86  mov     cs:?NlGlobalChangeLogServiceBits@@3KA, 0; ulong NlGlobalChangeLogServiceBits
0x180016c90  mov     cs:?NlGlobalChangeLogWorkerThreadHandle@@3PEAXEA, 0; void * NlGlobalChangeLogWorkerThreadHandle
0x180016c9b  mov     cs:?NlGlobalChangeLogNotifyBrowser@@3HA, 0; int NlGlobalChangeLogNotifyBrowser
0x180016ca5  mov     cs:?NlGlobalChangeLogWorkerIsRunning@@3HA, 0; int NlGlobalChangeLogWorkerIsRunning
0x180016caf  mov     cs:?NlGlobalChangeLogDllUnloaded@@3HA, ebx; int NlGlobalChangeLogDllUnloaded
0x180016cb5  mov     cs:?NlGlobalChangeLogNetlogonState@@3W4_CHANGELOG_NETLOGON_STATE@@A, 0; _CHANGELOG_NETLOGON_STATE NlGlobalChangeLogNetlogonState
0x180016cbf  mov     cs:?NlGlobalChangeLogEvent@@3PEAXEA, 0; void * NlGlobalChangeLogEvent
0x180016cca  call    NetpEventlogOpen
0x180016ccf  mov     cs:?NlGlobalEventlogHandle@@3PEAXEA, rax; void * NlGlobalEventlogHandle
0x180016cd6  test    rax, rax
0x180016cd9  jnz     short loc_180016CF6
0x180016cdb  lea     rdx, aCannotNetpeven; "Cannot NetpEventlogOpen\n"
0x180016ce2  mov     ecx, 100h; unsigned int
0x180016ce7  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180016cec  mov     eax, 0C0000017h
0x180016cf1  jmp     loc_180016DA5
0x180016cf6  xor     r9d, r9d; lpName
0x180016cf9  xor     r8d, r8d; bInitialState
0x180016cfc  xor     edx, edx; bManualReset
0x180016cfe  xor     ecx, ecx; lpEventAttributes
0x180016d00  call    cs:__imp_CreateEventW
0x180016d07  nop     dword ptr [rax+rax+00h]
0x180016d0c  mov     cs:?NlGlobalChangeLogEvent@@3PEAXEA, rax; void * NlGlobalChangeLogEvent
0x180016d13  test    rax, rax
0x180016d16  jnz     short loc_180016D43
0x180016d18  call    cs:__imp_GetLastError
0x180016d1f  nop     dword ptr [rax+rax+00h]
0x180016d24  lea     rdx, aCannotCreateCh; "Cannot create ChangeLog Event %lu\n"
0x180016d2b  mov     r8d, eax
0x180016d2e  mov     ecx, 100h; unsigned int
0x180016d33  mov     ebx, eax
0x180016d35  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180016d3a  mov     ecx, ebx
0x180016d3c  call    NetpApiStatusToNtStatus
0x180016d41  jmp     short loc_180016DA5
0x180016d43  xor     r9d, r9d; lpName
0x180016d46  mov     r8d, ebx; bInitialState
0x180016d49  mov     edx, ebx; bManualReset
0x180016d4b  xor     ecx, ecx; lpEventAttributes
0x180016d4d  call    cs:__imp_CreateEventW
0x180016d54  nop     dword ptr [rax+rax+00h]
0x180016d59  mov     cs:?NlGlobalTrustInfoUpToDateEvent@@3PEAXEA, rax; void * NlGlobalTrustInfoUpToDateEvent
0x180016d60  test    rax, rax
0x180016d63  jnz     short loc_180016D7A
0x180016d65  call    cs:__imp_GetLastError
0x180016d6c  nop     dword ptr [rax+rax+00h]
0x180016d71  lea     rdx, aCannotCreateTr; "Cannot create TrustInfoUpToDate Event %"...
0x180016d78  jmp     short loc_180016D2B
0x180016d7a  lea     rcx, [rsp+28h+ProductType]; ProductType
0x180016d7f  call    cs:__imp_RtlGetNtProductType
0x180016d86  nop     dword ptr [rax+rax+00h]
0x180016d8b  test    al, al
0x180016d8d  jz      short loc_180016D93
0x180016d8f  mov     ebx, [rsp+28h+ProductType]
0x180016d93  sub     ebx, 2
0x180016d96  neg     ebx
0x180016d98  sbb     eax, eax
0x180016d9a  add     eax, 3
0x180016d9d  mov     cs:?NlGlobalChangeLogRole@@3W4_CHANGELOG_ROLE@@A, eax; _CHANGELOG_ROLE NlGlobalChangeLogRole
0x180016da3  xor     eax, eax
0x180016da5  mov     rbx, [rsp+28h+arg_8]
0x180016daa  add     rsp, 20h
0x180016dae  pop     rdi
0x180016daf  retn
```
