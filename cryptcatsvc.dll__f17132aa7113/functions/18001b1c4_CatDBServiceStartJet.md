# _CatDBServiceStartJet

- ea: `0x18001b1c4`
- end: `0x18001b317`
- name: `_CatDBServiceStartJet`
- size: `339`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task`

## callers

- `0x18000ad54`

## callees

- `0x18000a59c`
- `0x1800190f8`
- `0x180019c8c`
- `0x18001b1c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b1ee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b1ee`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001b245`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001b245`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b2d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b2d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b269`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b269`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b2e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b2f4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b2e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b2f4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001b299`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001b299`

## pseudocode

```c
__int64 CatDBServiceStartJet()
{
  unsigned int v0; // ebx
  unsigned int v1; // edx
  unsigned __int16 *v2; // rcx
  DWORD LastError; // eax
  DWORD v4; // esi
  int v5; // edi
  DWORD TickCount; // eax
  unsigned int v7; // edx
  unsigned __int16 *v8; // rcx
  unsigned int v10; // edx
  unsigned __int16 *v11; // rcx
  int v12; // [rsp+28h] [rbp-30h]

  if ( g_fDBSvcInitialized || g_fShuttingDown )
  {
    SetLastError(0x420u);
    ErrLog_LogError(v11, v10, 0x21A6u, 0, 0, v12);
    return 0;
  }
  else
  {
    EnterCriticalSection(&g_JetDBOpenCS);
    v0 = 1;
    g_dwJetDBState = 2;
    g_fJetDBFirstPendingOpen = 1;
    g_fJetDBServiceStop = 0;
    g_dwJetDBOpenRefCnt = 0;
    g_dwJetDBPendingOpenRefCnt = 0;
    g_pJetDBPendingOpenHead = 0;
    g_hJetDBOpenThread = 0;
    g_hJetDBOpenThreadWaitEvent = 0;
    g_fJetDBFreeze = 0;
    g_hJetDBFreezeWaitEvent = 0;
    g_hJetDBServiceStopWaitEvent = CreateEventW(0, 0, 0, 0);
    if ( g_hJetDBServiceStopWaitEvent )
    {
      v4 = 0;
      if ( (_DWORD)qword_180032708 != -1 && !dword_180032710 && (unsigned int)CatDBHasCryptSvcSidDaclAce() )
      {
        v5 = 0;
        TickCount = GetTickCount();
        if ( (unsigned int)qword_180032708 > TickCount )
          v5 = qword_180032708 - TickCount;
        if ( !(unsigned int)CatDBCreateOpenJetThread(1, v5, -2) )
          ErrLog_LogError(v8, v7, 0x21D4u, 0, 0, v12);
      }
    }
    else
    {
      ErrLog_LogError(v2, v1, 0x21BFu, 0, 0, v12);
      LastError = GetLastError();
      v0 = 0;
      g_dwJetDBState = 0;
      v4 = LastError;
    }
    LeaveCriticalSection(&g_JetDBOpenCS);
    if ( !v0 )
      SetLastError(v4);
    return v0;
  }
}

```

## disassembly

```asm
0x18001b1c4  push    rbx
0x18001b1c6  push    rbp
0x18001b1c7  push    rsi
0x18001b1c8  push    rdi
0x18001b1c9  sub     rsp, 38h
0x18001b1cd  xor     ebp, ebp
0x18001b1cf  cmp     cs:?g_fDBSvcInitialized@@3HA, ebp; int g_fDBSvcInitialized
0x18001b1d5  jnz     loc_18001B2EF
0x18001b1db  cmp     cs:?g_fShuttingDown@@3HA, ebp; int g_fShuttingDown
0x18001b1e1  jnz     loc_18001B2EF
0x18001b1e7  lea     rcx, ?g_JetDBOpenCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001b1ee  call    cs:__imp_EnterCriticalSection
0x18001b1f4  lea     ebx, [rbp+1]
0x18001b1f7  mov     cs:?g_dwJetDBState@@3KA, 2; ulong g_dwJetDBState
0x18001b201  xor     r9d, r9d; lpName
0x18001b204  mov     cs:?g_fJetDBFirstPendingOpen@@3HA, ebx; int g_fJetDBFirstPendingOpen
0x18001b20a  xor     r8d, r8d; bInitialState
0x18001b20d  mov     cs:?g_fJetDBServiceStop@@3HA, ebp; int g_fJetDBServiceStop
0x18001b213  xor     edx, edx; bManualReset
0x18001b215  mov     cs:?g_dwJetDBOpenRefCnt@@3KA, ebp; ulong g_dwJetDBOpenRefCnt
0x18001b21b  xor     ecx, ecx; lpEventAttributes
0x18001b21d  mov     cs:?g_dwJetDBPendingOpenRefCnt@@3KA, ebp; ulong g_dwJetDBPendingOpenRefCnt
0x18001b223  mov     cs:?g_pJetDBPendingOpenHead@@3PEAU_JET_DB_PENDING_OPEN_STRUCT@@EA, rbp; _JET_DB_PENDING_OPEN_STRUCT * g_pJetDBPendingOpenHead
0x18001b22a  mov     cs:?g_hJetDBOpenThread@@3PEAXEA, rbp; void * g_hJetDBOpenThread
0x18001b231  mov     cs:?g_hJetDBOpenThreadWaitEvent@@3PEAXEA, rbp; void * g_hJetDBOpenThreadWaitEvent
0x18001b238  mov     cs:?g_fJetDBFreeze@@3HA, ebp; int g_fJetDBFreeze
0x18001b23e  mov     cs:?g_hJetDBFreezeWaitEvent@@3PEAXEA, rbp; void * g_hJetDBFreezeWaitEvent
0x18001b245  call    cs:__imp_CreateEventW
0x18001b24b  mov     cs:?g_hJetDBServiceStopWaitEvent@@3PEAXEA, rax; void * g_hJetDBServiceStopWaitEvent
0x18001b252  test    rax, rax
0x18001b255  jnz     short loc_18001B27B
0x18001b257  xor     r9d, r9d; unsigned int
0x18001b25a  mov     [rsp+58h+var_38], ebp; int
0x18001b25e  mov     r8d, 21BFh; unsigned int
0x18001b264  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001b269  call    cs:__imp_GetLastError
0x18001b26f  mov     ebx, ebp
0x18001b271  mov     cs:?g_dwJetDBState@@3KA, ebp; ulong g_dwJetDBState
0x18001b277  mov     esi, eax
0x18001b279  jmp     short loc_18001B2D2
0x18001b27b  cmp     dword ptr cs:qword_180032708, 0FFFFFFFFh
0x18001b282  mov     esi, ebp
0x18001b284  jz      short loc_18001B2D2
0x18001b286  cmp     cs:dword_180032710, ebp
0x18001b28c  jnz     short loc_18001B2D2
0x18001b28e  call    _CatDBHasCryptSvcSidDaclAce
0x18001b293  test    eax, eax
0x18001b295  jz      short loc_18001B2D2
0x18001b297  mov     edi, ebp
0x18001b299  call    cs:__imp_GetTickCount
0x18001b29f  mov     ecx, dword ptr cs:qword_180032708
0x18001b2a5  cmp     ecx, eax
0x18001b2a7  jbe     short loc_18001B2AD
0x18001b2a9  mov     edi, ecx
0x18001b2ab  sub     edi, eax
0x18001b2ad  mov     r8d, 0FFFFFFFEh
0x18001b2b3  mov     edx, edi
0x18001b2b5  mov     ecx, ebx
0x18001b2b7  call    _CatDBCreateOpenJetThread
0x18001b2bc  test    eax, eax
0x18001b2be  jnz     short loc_18001B2D2
0x18001b2c0  xor     r9d, r9d; unsigned int
0x18001b2c3  mov     [rsp+58h+var_38], ebp; int
0x18001b2c7  mov     r8d, 21D4h; unsigned int
0x18001b2cd  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001b2d2  lea     rcx, ?g_JetDBOpenCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001b2d9  call    cs:__imp_LeaveCriticalSection
0x18001b2df  test    ebx, ebx
0x18001b2e1  jnz     short loc_18001B2EB
0x18001b2e3  mov     ecx, esi; dwErrCode
0x18001b2e5  call    cs:__imp_SetLastError
0x18001b2eb  mov     eax, ebx
0x18001b2ed  jmp     short loc_18001B30E
0x18001b2ef  mov     ecx, 420h; dwErrCode
0x18001b2f4  call    cs:__imp_SetLastError
0x18001b2fa  xor     r9d, r9d; unsigned int
0x18001b2fd  mov     [rsp+58h+var_38], ebp; int
0x18001b301  mov     r8d, 21A6h; unsigned int
0x18001b307  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001b30c  xor     eax, eax
0x18001b30e  add     rsp, 38h
0x18001b312  pop     rdi
0x18001b313  pop     rsi
0x18001b314  pop     rbp
0x18001b315  pop     rbx
0x18001b316  retn
```
