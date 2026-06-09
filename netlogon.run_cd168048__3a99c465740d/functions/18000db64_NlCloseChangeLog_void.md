# NlCloseChangeLog(void)

- ea: `0x18000db64`
- end: `0x18000dcfa`
- name: `?NlCloseChangeLog@@YAJXZ`
- size: `406`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180079874`

## callees

- `0x180007518`
- `0x18000db64`
- `0x18000dd00`
- `0x18000dd38`
- `0x18000dd78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000dc41`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000dc41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dba1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dbc4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dba1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dbc4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dc50`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dca4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dcc7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dc50`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dca4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dcc7`
- `LSASRV!LsaIUnregisterAllPolicyChangeNotificationCallback` at `0x18000db71`
- `LSASRV!LsaIUnregisterAllPolicyChangeNotificationCallback` at `0x18000db71`
- `ntdll!RtlLeaveCriticalSection` at `0x18000dc23`
- `ntdll!RtlLeaveCriticalSection` at `0x18000dc23`
- `ntdll!RtlDeleteCriticalSection` at `0x18000dc70`
- `ntdll!RtlDeleteCriticalSection` at `0x18000dc8c`
- `ntdll!RtlDeleteCriticalSection` at `0x18000dce5`
- `ntdll!RtlDeleteCriticalSection` at `0x18000dc70`
- `ntdll!RtlDeleteCriticalSection` at `0x18000dc8c`
- `ntdll!RtlDeleteCriticalSection` at `0x18000dce5`
- `ntdll!RtlEnterCriticalSection` at `0x18000dbe7`
- `ntdll!RtlEnterCriticalSection` at `0x18000dbe7`

## string_xrefs

- `0x18000dc09`: `onecore\ds\netapi\svcdlls\logonsrv\server\changelg.cxx`
- `0x18000dc10`: `IsListEmpty( &NlGlobalChangeLogNotifications )`

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
      0x685u,
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
0x18000db64  push    rbx
0x18000db66  sub     rsp, 20h
0x18000db6a  lea     rcx, ?I_NetNotifyLsaPolicyChange@@YAXW4_POLICY_NOTIFICATION_INFORMATION_CLASS@@@Z; I_NetNotifyLsaPolicyChange(_POLICY_NOTIFICATION_INFORMATION_CLASS)
0x18000db71  call    cs:__imp_LsaIUnregisterAllPolicyChangeNotificationCallback
0x18000db78  nop     dword ptr [rax+rax+00h]
0x18000db7d  test    eax, eax
0x18000db7f  jns     short loc_18000DB95
0x18000db81  mov     r8d, eax
0x18000db84  lea     rdx, aFailedToLsaiun; "Failed to LsaIUnregisterPolicyChangeNot"...
0x18000db8b  mov     ecx, 100h; unsigned int
0x18000db90  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18000db95  mov     rcx, cs:?NlGlobalChangeLogEvent@@3PEAXEA; hObject
0x18000db9c  test    rcx, rcx
0x18000db9f  jz      short loc_18000DBB8
0x18000dba1  call    cs:__imp_CloseHandle
0x18000dba8  nop     dword ptr [rax+rax+00h]
0x18000dbad  mov     cs:?NlGlobalChangeLogEvent@@3PEAXEA, 0; void * NlGlobalChangeLogEvent
0x18000dbb8  mov     rcx, cs:?NlGlobalTrustInfoUpToDateEvent@@3PEAXEA; hObject
0x18000dbbf  test    rcx, rcx
0x18000dbc2  jz      short loc_18000DBDB
0x18000dbc4  call    cs:__imp_CloseHandle
0x18000dbcb  nop     dword ptr [rax+rax+00h]
0x18000dbd0  mov     cs:?NlGlobalTrustInfoUpToDateEvent@@3PEAXEA, 0; void * NlGlobalTrustInfoUpToDateEvent
0x18000dbdb  call    ?NlStopChangeLogWorker@@YAXXZ; NlStopChangeLogWorker(void)
0x18000dbe0  lea     rcx, ?NlGlobalChangeLogCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18000dbe7  call    cs:__imp_RtlEnterCriticalSection
0x18000dbee  nop     dword ptr [rax+rax+00h]
0x18000dbf3  lea     rax, ?NlGlobalChangeLogNotifications@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalChangeLogNotifications
0x18000dbfa  cmp     cs:?NlGlobalChangeLogNotifications@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY NlGlobalChangeLogNotifications
0x18000dc01  jz      short loc_18000DC1C
0x18000dc03  mov     r8d, 685h; unsigned int
0x18000dc09  lea     rdx, aOnecoreDsNetap_0; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18000dc10  lea     rcx, aIslistemptyNlg_1; "IsListEmpty( &NlGlobalChangeLogNotifica"...
0x18000dc17  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18000dc1c  lea     rcx, ?NlGlobalChangeLogCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18000dc23  call    cs:__imp_RtlLeaveCriticalSection
0x18000dc2a  nop     dword ptr [rax+rax+00h]
0x18000dc2f  mov     rbx, cs:?NlGlobalEventlogHandle@@3PEAXEA; void * NlGlobalEventlogHandle
0x18000dc36  mov     rcx, rbx
0x18000dc39  call    NetpEventlogClearList
0x18000dc3e  mov     rcx, rbx; lpCriticalSection
0x18000dc41  call    cs:__imp_DeleteCriticalSection
0x18000dc48  nop     dword ptr [rax+rax+00h]
0x18000dc4d  mov     rcx, rbx; hMem
0x18000dc50  call    cs:__imp_LocalFree
0x18000dc57  nop     dword ptr [rax+rax+00h]
0x18000dc5c  xor     ebx, ebx
0x18000dc5e  lea     rax, ?NlGlobalSecPkgCritSect@@3PAU_SAFE_CRITICAL_SECTION@@A; _SAFE_CRITICAL_SECTION near * NlGlobalSecPkgCritSect
0x18000dc65  lea     rcx, [rbx+rbx*2]
0x18000dc69  shl     rcx, 4
0x18000dc6d  add     rcx, rax; CriticalSection
0x18000dc70  call    cs:__imp_RtlDeleteCriticalSection
0x18000dc77  nop     dword ptr [rax+rax+00h]
0x18000dc7c  inc     rbx
0x18000dc7f  cmp     rbx, 10h
0x18000dc83  jnz     short loc_18000DC5E
0x18000dc85  lea     rcx, ?NlGlobalChangeLogCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18000dc8c  call    cs:__imp_RtlDeleteCriticalSection
0x18000dc93  nop     dword ptr [rax+rax+00h]
0x18000dc98  mov     rcx, cs:?NlGlobalLogFileOutputBuffer@@3PEAGEA; hMem
0x18000dc9f  test    rcx, rcx
0x18000dca2  jz      short loc_18000DCBB
0x18000dca4  call    cs:__imp_LocalFree
0x18000dcab  nop     dword ptr [rax+rax+00h]
0x18000dcb0  mov     cs:?NlGlobalLogFileOutputBuffer@@3PEAGEA, 0; ushort * NlGlobalLogFileOutputBuffer
0x18000dcbb  mov     rcx, cs:?NlGlobalLogFileUtf8Buffer@@3PEAEEA; hMem
0x18000dcc2  test    rcx, rcx
0x18000dcc5  jz      short loc_18000DCDE
0x18000dcc7  call    cs:__imp_LocalFree
0x18000dcce  nop     dword ptr [rax+rax+00h]
0x18000dcd3  mov     cs:?NlGlobalLogFileUtf8Buffer@@3PEAEEA, 0; uchar * NlGlobalLogFileUtf8Buffer
0x18000dcde  lea     rcx, ?NlGlobalLogFileCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18000dce5  call    cs:__imp_RtlDeleteCriticalSection
0x18000dcec  nop     dword ptr [rax+rax+00h]
0x18000dcf1  xor     eax, eax
0x18000dcf3  add     rsp, 20h
0x18000dcf7  pop     rbx
0x18000dcf8  retn
```
