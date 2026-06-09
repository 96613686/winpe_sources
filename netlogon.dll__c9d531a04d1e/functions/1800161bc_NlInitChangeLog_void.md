# NlInitChangeLog(void)

- ea: `0x1800161bc`
- end: `0x180016364`
- name: `?NlInitChangeLog@@YAJXZ`
- size: `424`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x18000d1f0`

## callees

- `0x180007278`
- `0x18000d100`
- `0x1800161bc`
- `0x180084a84`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800162d2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016313`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800162d2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016313`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800162e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016325`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800162e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016325`
- `ntdll!RtlInitializeCriticalSection` at `0x1800161d5`
- `ntdll!RtlInitializeCriticalSection` at `0x1800161e2`
- `ntdll!RtlInitializeCriticalSection` at `0x1800161ff`
- `ntdll!RtlInitializeCriticalSection` at `0x1800161d5`
- `ntdll!RtlInitializeCriticalSection` at `0x1800161e2`
- `ntdll!RtlInitializeCriticalSection` at `0x1800161ff`
- `ntdll!RtlGetNtProductType` at `0x180016339`
- `ntdll!RtlGetNtProductType` at `0x180016339`

## string_xrefs

- `0x1800162ad`: `Cannot NetpEventlogOpen\n`
- `0x1800162ea`: `Cannot create ChangeLog Event %lu\n`
- `0x18001632b`: `Cannot create TrustInfoUpToDate Event %lu\n`

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
  qword_1800F0A38 = (__int64)&NlGlobalChangeLogNotifications;
  NlGlobalChangeLogNotifications.Flink = &NlGlobalChangeLogNotifications;
  NlGlobalLogFile = (HANDLE)-1LL;
  dword_1800F1104 = 20000000;
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
0x1800161bc  mov     [rsp+arg_8], rbx
0x1800161c1  push    rdi
0x1800161c2  sub     rsp, 20h
0x1800161c6  lea     rcx, ?NlGlobalLogFileCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x1800161cd  mov     [rsp+28h+ProductType], 0
0x1800161d5  call    cs:__imp_RtlInitializeCriticalSection
0x1800161db  lea     rcx, ?NlGlobalChangeLogCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x1800161e2  call    cs:__imp_RtlInitializeCriticalSection
0x1800161e8  xor     edi, edi
0x1800161ea  lea     ebx, [rdi+1]
0x1800161ed  lea     rax, ?NlGlobalSecPkgCritSect@@3PAU_SAFE_CRITICAL_SECTION@@A; _SAFE_CRITICAL_SECTION near * NlGlobalSecPkgCritSect
0x1800161f4  lea     rcx, [rdi+rdi*2]
0x1800161f8  shl     rcx, 4
0x1800161fc  add     rcx, rax; CriticalSection
0x1800161ff  call    cs:__imp_RtlInitializeCriticalSection
0x180016205  add     rdi, rbx
0x180016208  cmp     rdi, 10h
0x18001620c  jnz     short loc_1800161ED
0x18001620e  lea     rax, ?NlGlobalChangeLogNotifications@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalChangeLogNotifications
0x180016215  mov     cs:?NlGlobalParameters@@3U_NETLOGON_PARAMETERS@@A, 0FFFFFFFFh; _NETLOGON_PARAMETERS NlGlobalParameters
0x18001621f  mov     cs:qword_1800F0A38, rax
0x180016226  mov     cs:?NlGlobalChangeLogNotifications@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY NlGlobalChangeLogNotifications
0x18001622d  mov     cs:?NlGlobalLogFile@@3PEAXEA, 0FFFFFFFFFFFFFFFFh; void * NlGlobalLogFile
0x180016238  mov     cs:dword_1800F1104, 1312D00h
0x180016242  mov     cs:?NlGlobalLogFileOutputBuffer@@3PEAGEA, 0; ushort * NlGlobalLogFileOutputBuffer
0x18001624d  mov     cs:?NlGlobalLogFileUtf8Buffer@@3PEAEEA, 0; uchar * NlGlobalLogFileUtf8Buffer
0x180016258  mov     cs:?NlGlobalChangeLogServiceBits@@3KA, 0; ulong NlGlobalChangeLogServiceBits
0x180016262  mov     cs:?NlGlobalChangeLogWorkerThreadHandle@@3PEAXEA, 0; void * NlGlobalChangeLogWorkerThreadHandle
0x18001626d  mov     cs:?NlGlobalChangeLogNotifyBrowser@@3HA, 0; int NlGlobalChangeLogNotifyBrowser
0x180016277  mov     cs:?NlGlobalChangeLogWorkerIsRunning@@3HA, 0; int NlGlobalChangeLogWorkerIsRunning
0x180016281  mov     cs:?NlGlobalChangeLogDllUnloaded@@3HA, ebx; int NlGlobalChangeLogDllUnloaded
0x180016287  mov     cs:?NlGlobalChangeLogNetlogonState@@3W4_CHANGELOG_NETLOGON_STATE@@A, 0; _CHANGELOG_NETLOGON_STATE NlGlobalChangeLogNetlogonState
0x180016291  mov     cs:?NlGlobalChangeLogEvent@@3PEAXEA, 0; void * NlGlobalChangeLogEvent
0x18001629c  call    NetpEventlogOpen
0x1800162a1  mov     cs:?NlGlobalEventlogHandle@@3PEAXEA, rax; void * NlGlobalEventlogHandle
0x1800162a8  test    rax, rax
0x1800162ab  jnz     short loc_1800162C8
0x1800162ad  lea     rdx, aCannotNetpeven; "Cannot NetpEventlogOpen\n"
0x1800162b4  mov     ecx, 100h; unsigned int
0x1800162b9  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800162be  mov     eax, 0C0000017h
0x1800162c3  jmp     loc_180016359
0x1800162c8  xor     r9d, r9d; lpName
0x1800162cb  xor     r8d, r8d; bInitialState
0x1800162ce  xor     edx, edx; bManualReset
0x1800162d0  xor     ecx, ecx; lpEventAttributes
0x1800162d2  call    cs:__imp_CreateEventW
0x1800162d8  mov     cs:?NlGlobalChangeLogEvent@@3PEAXEA, rax; void * NlGlobalChangeLogEvent
0x1800162df  test    rax, rax
0x1800162e2  jnz     short loc_180016309
0x1800162e4  call    cs:__imp_GetLastError
0x1800162ea  lea     rdx, aCannotCreateCh; "Cannot create ChangeLog Event %lu\n"
0x1800162f1  mov     r8d, eax
0x1800162f4  mov     ecx, 100h; unsigned int
0x1800162f9  mov     ebx, eax
0x1800162fb  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180016300  mov     ecx, ebx
0x180016302  call    NetpApiStatusToNtStatus
0x180016307  jmp     short loc_180016359
0x180016309  xor     r9d, r9d; lpName
0x18001630c  mov     r8d, ebx; bInitialState
0x18001630f  mov     edx, ebx; bManualReset
0x180016311  xor     ecx, ecx; lpEventAttributes
0x180016313  call    cs:__imp_CreateEventW
0x180016319  mov     cs:?NlGlobalTrustInfoUpToDateEvent@@3PEAXEA, rax; void * NlGlobalTrustInfoUpToDateEvent
0x180016320  test    rax, rax
0x180016323  jnz     short loc_180016334
0x180016325  call    cs:__imp_GetLastError
0x18001632b  lea     rdx, aCannotCreateTr; "Cannot create TrustInfoUpToDate Event %"...
0x180016332  jmp     short loc_1800162F1
0x180016334  lea     rcx, [rsp+28h+ProductType]; ProductType
0x180016339  call    cs:__imp_RtlGetNtProductType
0x18001633f  test    al, al
0x180016341  jz      short loc_180016347
0x180016343  mov     ebx, [rsp+28h+ProductType]
0x180016347  sub     ebx, 2
0x18001634a  neg     ebx
0x18001634c  sbb     eax, eax
0x18001634e  add     eax, 3
0x180016351  mov     cs:?NlGlobalChangeLogRole@@3W4_CHANGELOG_ROLE@@A, eax; _CHANGELOG_ROLE NlGlobalChangeLogRole
0x180016357  xor     eax, eax
0x180016359  mov     rbx, [rsp+28h+arg_8]
0x18001635e  add     rsp, 20h
0x180016362  pop     rdi
0x180016363  retn
```
