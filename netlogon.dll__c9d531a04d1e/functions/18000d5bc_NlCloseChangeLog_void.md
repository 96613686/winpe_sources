# NlCloseChangeLog(void)

- ea: `0x18000d5bc`
- end: `0x18000d709`
- name: `?NlCloseChangeLog@@YAJXZ`
- size: `333`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18000d1f0`

## callees

- `0x180007278`
- `0x18000d5bc`
- `0x18000d710`
- `0x18000d744`
- `0x18000d77c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d67b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d67b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d5f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d610`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d5f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d610`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d684`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d6c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d6e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d684`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d6c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d6e3`
- `LSASRV!LsaIUnregisterAllPolicyChangeNotificationCallback` at `0x18000d5c9`
- `LSASRV!LsaIUnregisterAllPolicyChangeNotificationCallback` at `0x18000d5c9`
- `ntdll!RtlLeaveCriticalSection` at `0x18000d663`
- `ntdll!RtlLeaveCriticalSection` at `0x18000d663`
- `ntdll!RtlDeleteCriticalSection` at `0x18000d69e`
- `ntdll!RtlDeleteCriticalSection` at `0x18000d6b4`
- `ntdll!RtlDeleteCriticalSection` at `0x18000d6fb`
- `ntdll!RtlDeleteCriticalSection` at `0x18000d69e`
- `ntdll!RtlDeleteCriticalSection` at `0x18000d6b4`
- `ntdll!RtlDeleteCriticalSection` at `0x18000d6fb`
- `ntdll!RtlEnterCriticalSection` at `0x18000d62d`
- `ntdll!RtlEnterCriticalSection` at `0x18000d62d`

## string_xrefs

- `0x18000d649`: `onecore\ds\netapi\svcdlls\logonsrv\server\changelg.cxx`
- `0x18000d650`: `IsListEmpty( &NlGlobalChangeLogNotifications )`

## pseudocode

```c
__int64 NlCloseChangeLog(void)
{
  int v0; // eax
  char *v1; // r9
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  __int64 i; // rbx

  v0 = LsaIUnregisterAllPolicyChangeNotificationCallback(I_NetNotifyLsaPolicyChange);
  if ( v0 < 0 )
    NlPrintRoutine(0x100u, L"Failed to LsaIUnregisterPolicyChangeNotificationCallback. %lX\n", (unsigned int)v0);
  if ( NlGlobalChangeLogEvent )
  {
    CloseHandle(NlGlobalChangeLogEvent);
    NlGlobalChangeLogEvent = 0;
  }
  if ( NlGlobalTrustInfoUpToDateEvent )
  {
    CloseHandle(NlGlobalTrustInfoUpToDateEvent);
    NlGlobalTrustInfoUpToDateEvent = 0;
  }
  NlStopChangeLogWorker();
  RtlEnterCriticalSection(&NlGlobalChangeLogCritSect);
  if ( NlGlobalChangeLogNotifications.Flink != &NlGlobalChangeLogNotifications )
    NlAssertFailed(
      "IsListEmpty( &NlGlobalChangeLogNotifications )",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\changelg.cxx",
      1669,
      v1);
  RtlLeaveCriticalSection(&NlGlobalChangeLogCritSect);
  v2 = NlGlobalEventlogHandle;
  NetpEventlogClearList(NlGlobalEventlogHandle);
  DeleteCriticalSection(v2);
  LocalFree(v2);
  for ( i = 0; i != 16; ++i )
    RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(&NlGlobalSecPkgCritSect + 6 * i));
  RtlDeleteCriticalSection(&NlGlobalChangeLogCritSect);
  if ( NlGlobalLogFileOutputBuffer )
  {
    LocalFree((HLOCAL)NlGlobalLogFileOutputBuffer);
    NlGlobalLogFileOutputBuffer = 0;
  }
  if ( NlGlobalLogFileUtf8Buffer )
  {
    LocalFree(NlGlobalLogFileUtf8Buffer);
    NlGlobalLogFileUtf8Buffer = 0;
  }
  RtlDeleteCriticalSection(&NlGlobalLogFileCritSect);
  return 0;
}

```

## disassembly

```asm
0x18000d5bc  push    rbx
0x18000d5be  sub     rsp, 20h
0x18000d5c2  lea     rcx, ?I_NetNotifyLsaPolicyChange@@YAXW4_POLICY_NOTIFICATION_INFORMATION_CLASS@@@Z; I_NetNotifyLsaPolicyChange(_POLICY_NOTIFICATION_INFORMATION_CLASS)
0x18000d5c9  call    cs:__imp_LsaIUnregisterAllPolicyChangeNotificationCallback
0x18000d5cf  test    eax, eax
0x18000d5d1  jns     short loc_18000D5E7
0x18000d5d3  mov     r8d, eax
0x18000d5d6  lea     rdx, aFailedToLsaiun; "Failed to LsaIUnregisterPolicyChangeNot"...
0x18000d5dd  mov     ecx, 100h; unsigned int
0x18000d5e2  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18000d5e7  mov     rcx, cs:?NlGlobalChangeLogEvent@@3PEAXEA; hObject
0x18000d5ee  test    rcx, rcx
0x18000d5f1  jz      short loc_18000D604
0x18000d5f3  call    cs:__imp_CloseHandle
0x18000d5f9  mov     cs:?NlGlobalChangeLogEvent@@3PEAXEA, 0; void * NlGlobalChangeLogEvent
0x18000d604  mov     rcx, cs:?NlGlobalTrustInfoUpToDateEvent@@3PEAXEA; hObject
0x18000d60b  test    rcx, rcx
0x18000d60e  jz      short loc_18000D621
0x18000d610  call    cs:__imp_CloseHandle
0x18000d616  mov     cs:?NlGlobalTrustInfoUpToDateEvent@@3PEAXEA, 0; void * NlGlobalTrustInfoUpToDateEvent
0x18000d621  call    ?NlStopChangeLogWorker@@YAXXZ; NlStopChangeLogWorker(void)
0x18000d626  lea     rcx, ?NlGlobalChangeLogCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18000d62d  call    cs:__imp_RtlEnterCriticalSection
0x18000d633  lea     rax, ?NlGlobalChangeLogNotifications@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalChangeLogNotifications
0x18000d63a  cmp     cs:?NlGlobalChangeLogNotifications@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY NlGlobalChangeLogNotifications
0x18000d641  jz      short loc_18000D65C
0x18000d643  mov     r8d, 685h; unsigned int
0x18000d649  lea     rdx, aOnecoreDsNetap_0; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18000d650  lea     rcx, aIslistemptyNlg_1; "IsListEmpty( &NlGlobalChangeLogNotifica"...
0x18000d657  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18000d65c  lea     rcx, ?NlGlobalChangeLogCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18000d663  call    cs:__imp_RtlLeaveCriticalSection
0x18000d669  mov     rbx, cs:?NlGlobalEventlogHandle@@3PEAXEA; void * NlGlobalEventlogHandle
0x18000d670  mov     rcx, rbx
0x18000d673  call    NetpEventlogClearList
0x18000d678  mov     rcx, rbx; lpCriticalSection
0x18000d67b  call    cs:__imp_DeleteCriticalSection
0x18000d681  mov     rcx, rbx; hMem
0x18000d684  call    cs:__imp_LocalFree
0x18000d68a  xor     ebx, ebx
0x18000d68c  lea     rax, ?NlGlobalSecPkgCritSect@@3PAU_SAFE_CRITICAL_SECTION@@A; _SAFE_CRITICAL_SECTION near * NlGlobalSecPkgCritSect
0x18000d693  lea     rcx, [rbx+rbx*2]
0x18000d697  shl     rcx, 4
0x18000d69b  add     rcx, rax; CriticalSection
0x18000d69e  call    cs:__imp_RtlDeleteCriticalSection
0x18000d6a4  inc     rbx
0x18000d6a7  cmp     rbx, 10h
0x18000d6ab  jnz     short loc_18000D68C
0x18000d6ad  lea     rcx, ?NlGlobalChangeLogCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18000d6b4  call    cs:__imp_RtlDeleteCriticalSection
0x18000d6ba  mov     rcx, cs:?NlGlobalLogFileOutputBuffer@@3PEAGEA; hMem
0x18000d6c1  test    rcx, rcx
0x18000d6c4  jz      short loc_18000D6D7
0x18000d6c6  call    cs:__imp_LocalFree
0x18000d6cc  mov     cs:?NlGlobalLogFileOutputBuffer@@3PEAGEA, 0; ushort * NlGlobalLogFileOutputBuffer
0x18000d6d7  mov     rcx, cs:?NlGlobalLogFileUtf8Buffer@@3PEAEEA; hMem
0x18000d6de  test    rcx, rcx
0x18000d6e1  jz      short loc_18000D6F4
0x18000d6e3  call    cs:__imp_LocalFree
0x18000d6e9  mov     cs:?NlGlobalLogFileUtf8Buffer@@3PEAEEA, 0; uchar * NlGlobalLogFileUtf8Buffer
0x18000d6f4  lea     rcx, ?NlGlobalLogFileCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18000d6fb  call    cs:__imp_RtlDeleteCriticalSection
0x18000d701  xor     eax, eax
0x18000d703  add     rsp, 20h
0x18000d707  pop     rbx
0x18000d708  retn
```
