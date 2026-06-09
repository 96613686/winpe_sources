# _CatDBFreezeJet

- ea: `0x180019a7c`
- end: `0x180019c84`
- name: `_CatDBFreezeJet`
- size: `520`
- prototype: `__int64 __fastcall(int)`
- caller_count: `6`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180002410`
- `0x180012ce0`
- `0x18001ad58`
- `0x18001caa0`
- `0x18001cca0`
- `0x18001e850`

## callees

- `0x180002b90`
- `0x18000a59c`
- `0x180019a7c`
- `0x18001b620`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180019b59`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180019b59`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019aab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019bb1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019bbc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019aab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019bb1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019bbc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180019af2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180019af2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180019b8a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180019b8a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019b62`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019b73`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019c46`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019b62`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019b73`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019c46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019ba6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019be8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019ba6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019be8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c34`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019abe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019b3c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019bd0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019c1c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019c52`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019c61`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019abe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019b3c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019bd0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019c1c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019c52`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019c61`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019c08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019c08`

## pseudocode

```c
__int64 __fastcall CatDBFreezeJet(int a1)
{
  unsigned int v2; // edx
  HANDLE v3; // rcx
  unsigned int v4; // r8d
  unsigned int v5; // ebx
  unsigned int v6; // edx
  unsigned __int16 *v7; // rcx
  unsigned int v8; // r8d
  unsigned int v9; // edx
  unsigned __int16 *v10; // rcx
  DWORD LastError; // edi
  unsigned int v13; // edx
  unsigned __int16 *v14; // rcx
  int v15; // [rsp+28h] [rbp-30h]

  if ( !g_fDBSvcInitialized || g_fShuttingDown )
  {
    SetLastError(0x426u);
    ErrLog_LogError(v14, v13, 0x2006u, 0, 0, v15);
    return 0;
  }
  EnterCriticalSection(&g_JetDBOpenCS);
  if ( !g_fJetDBServiceStop )
  {
    if ( g_fJetDBFreeze || g_hJetDBFreezeWaitEvent )
    {
      SetLastError(0xB7u);
      v4 = 8214;
      goto LABEL_28;
    }
    g_hJetDBFreezeWaitEvent = CreateEventW(0, 0, 0, 0);
    v3 = g_hJetDBFreezeWaitEvent;
    if ( !g_hJetDBFreezeWaitEvent )
    {
      v4 = 8223;
      goto LABEL_28;
    }
    v5 = 1;
    g_fJetDBFreeze = 1;
    if ( g_dwJetDBState == 1 )
    {
      ++g_dwJetDBOpenRefCnt;
      LeaveCriticalSection(&g_JetDBOpenCS);
      _CatDBCloseJet(a1);
      goto LABEL_18;
    }
    if ( g_dwJetDBState == 2 )
      goto LABEL_15;
    if ( g_dwJetDBState != 3 )
    {
      if ( g_dwJetDBState - 4 >= 2 )
      {
        SetLastError(0x8000FFFF);
        v8 = 8258;
        goto LABEL_22;
      }
      goto LABEL_16;
    }
    v3 = g_hJetDBOpenThreadWaitEvent;
    if ( g_hJetDBOpenThreadWaitEvent )
LABEL_15:
      SetEvent(v3);
LABEL_16:
    LeaveCriticalSection(&g_JetDBOpenCS);
LABEL_18:
    if ( WaitForSingleObject(g_hJetDBFreezeWaitEvent, 0xFFFFFFFF) )
    {
      ErrLog_LogError(v10, v9, 0x2051u, 0, 0, v15);
      LastError = GetLastError();
      EnterCriticalSection(&g_JetDBOpenCS);
LABEL_23:
      v5 = 0;
      g_fJetDBFreeze = 0;
      goto LABEL_25;
    }
    EnterCriticalSection(&g_JetDBOpenCS);
    if ( g_dwJetDBState == 2 )
    {
      LastError = 0;
LABEL_25:
      if ( g_hJetDBFreezeWaitEvent )
      {
        CloseHandle(g_hJetDBFreezeWaitEvent);
        g_hJetDBFreezeWaitEvent = 0;
      }
      goto LABEL_29;
    }
    SetLastError(0x8000FFFF);
    v8 = 8282;
LABEL_22:
    ErrLog_LogError(v7, v6, v8, 0, 0, v15);
    LastError = GetLastError();
    goto LABEL_23;
  }
  SetLastError(0x426u);
  v4 = 8208;
LABEL_28:
  ErrLog_LogError((unsigned __int16 *)v3, v2, v4, 0, 0, v15);
  LastError = GetLastError();
  v5 = 0;
LABEL_29:
  CatDBSignalPendingJetFreezeOrStop();
  LeaveCriticalSection(&g_JetDBOpenCS);
  if ( !v5 )
    SetLastError(LastError);
  return v5;
}

```

## disassembly

```asm
0x180019a7c  push    rbx
0x180019a7e  push    rbp
0x180019a7f  push    rsi
0x180019a80  push    rdi
0x180019a81  sub     rsp, 38h
0x180019a85  xor     esi, esi
0x180019a87  mov     edi, ecx
0x180019a89  cmp     cs:?g_fDBSvcInitialized@@3HA, esi; int g_fDBSvcInitialized
0x180019a8f  jz      loc_180019C5C
0x180019a95  cmp     cs:?g_fShuttingDown@@3HA, esi; int g_fShuttingDown
0x180019a9b  jnz     loc_180019C5C
0x180019aa1  lea     rbp, ?g_JetDBOpenCS@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_JetDBOpenCS
0x180019aa8  mov     rcx, rbp; lpCriticalSection
0x180019aab  call    cs:__imp_EnterCriticalSection
0x180019ab1  cmp     cs:?g_fJetDBServiceStop@@3HA, esi; int g_fJetDBServiceStop
0x180019ab7  jz      short loc_180019ACF
0x180019ab9  mov     ecx, 426h; dwErrCode
0x180019abe  call    cs:__imp_SetLastError
0x180019ac4  mov     r8d, 2010h
0x180019aca  jmp     loc_180019C28
0x180019acf  cmp     cs:?g_fJetDBFreeze@@3HA, esi; int g_fJetDBFreeze
0x180019ad5  jnz     loc_180019C17
0x180019adb  cmp     cs:?g_hJetDBFreezeWaitEvent@@3PEAXEA, rsi; void * g_hJetDBFreezeWaitEvent
0x180019ae2  jnz     loc_180019C17
0x180019ae8  xor     r9d, r9d; lpName
0x180019aeb  xor     r8d, r8d; bInitialState
0x180019aee  xor     edx, edx; bManualReset
0x180019af0  xor     ecx, ecx; lpEventAttributes
0x180019af2  call    cs:__imp_CreateEventW
0x180019af8  mov     cs:?g_hJetDBFreezeWaitEvent@@3PEAXEA, rax; void * g_hJetDBFreezeWaitEvent
0x180019aff  mov     rcx, rax
0x180019b02  test    rax, rax
0x180019b05  jnz     short loc_180019B12
0x180019b07  mov     r8d, 201Fh
0x180019b0d  jmp     loc_180019C28
0x180019b12  mov     eax, cs:?g_dwJetDBState@@3KA; ulong g_dwJetDBState
0x180019b18  mov     ebx, 1
0x180019b1d  mov     cs:?g_fJetDBFreeze@@3HA, ebx; int g_fJetDBFreeze
0x180019b23  sub     eax, ebx
0x180019b25  jz      short loc_180019B6A
0x180019b27  sub     eax, ebx
0x180019b29  jz      short loc_180019B59
0x180019b2b  sub     eax, ebx
0x180019b2d  jz      short loc_180019B4D
0x180019b2f  sub     eax, ebx
0x180019b31  jz      short loc_180019B5F
0x180019b33  cmp     eax, ebx
0x180019b35  jz      short loc_180019B5F
0x180019b37  mov     ecx, 8000FFFFh; dwErrCode
0x180019b3c  call    cs:__imp_SetLastError
0x180019b42  mov     r8d, 2042h
0x180019b48  jmp     loc_180019BDC
0x180019b4d  mov     rcx, cs:?g_hJetDBOpenThreadWaitEvent@@3PEAXEA; hEvent
0x180019b54  test    rcx, rcx
0x180019b57  jz      short loc_180019B5F
0x180019b59  call    cs:__imp_SetEvent
0x180019b5f  mov     rcx, rbp; lpCriticalSection
0x180019b62  call    cs:__imp_LeaveCriticalSection
0x180019b68  jmp     short loc_180019B80
0x180019b6a  add     cs:?g_dwJetDBOpenRefCnt@@3KA, ebx; ulong g_dwJetDBOpenRefCnt
0x180019b70  mov     rcx, rbp; lpCriticalSection
0x180019b73  call    cs:__imp_LeaveCriticalSection
0x180019b79  mov     ecx, edi; int
0x180019b7b  call    ?_CatDBCloseJet@@YAXH@Z; _CatDBCloseJet(int)
0x180019b80  mov     rcx, cs:?g_hJetDBFreezeWaitEvent@@3PEAXEA; hHandle
0x180019b87  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180019b8a  call    cs:__imp_WaitForSingleObject
0x180019b90  test    eax, eax
0x180019b92  jz      short loc_180019BB9
0x180019b94  xor     r9d, r9d; unsigned int
0x180019b97  mov     [rsp+58h+var_38], esi; int
0x180019b9b  mov     r8d, 2051h; unsigned int
0x180019ba1  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180019ba6  call    cs:__imp_GetLastError
0x180019bac  mov     rcx, rbp; lpCriticalSection
0x180019baf  mov     edi, eax
0x180019bb1  call    cs:__imp_EnterCriticalSection
0x180019bb7  jmp     short loc_180019BF0
0x180019bb9  mov     rcx, rbp; lpCriticalSection
0x180019bbc  call    cs:__imp_EnterCriticalSection
0x180019bc2  cmp     cs:?g_dwJetDBState@@3KA, 2; ulong g_dwJetDBState
0x180019bc9  jz      short loc_180019BFA
0x180019bcb  mov     ecx, 8000FFFFh; dwErrCode
0x180019bd0  call    cs:__imp_SetLastError
0x180019bd6  mov     r8d, 205Ah; unsigned int
0x180019bdc  xor     r9d, r9d; unsigned int
0x180019bdf  mov     [rsp+58h+var_38], esi; int
0x180019be3  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180019be8  call    cs:__imp_GetLastError
0x180019bee  mov     edi, eax
0x180019bf0  mov     ebx, esi
0x180019bf2  mov     cs:?g_fJetDBFreeze@@3HA, esi; int g_fJetDBFreeze
0x180019bf8  jmp     short loc_180019BFC
0x180019bfa  mov     edi, esi
0x180019bfc  mov     rcx, cs:?g_hJetDBFreezeWaitEvent@@3PEAXEA; hObject
0x180019c03  test    rcx, rcx
0x180019c06  jz      short loc_180019C3E
0x180019c08  call    cs:__imp_CloseHandle
0x180019c0e  mov     cs:?g_hJetDBFreezeWaitEvent@@3PEAXEA, rsi; void * g_hJetDBFreezeWaitEvent
0x180019c15  jmp     short loc_180019C3E
0x180019c17  mov     ecx, 0B7h; dwErrCode
0x180019c1c  call    cs:__imp_SetLastError
0x180019c22  mov     r8d, 2016h; unsigned int
0x180019c28  xor     r9d, r9d; unsigned int
0x180019c2b  mov     [rsp+58h+var_38], esi; int
0x180019c2f  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180019c34  call    cs:__imp_GetLastError
0x180019c3a  mov     edi, eax
0x180019c3c  mov     ebx, esi
0x180019c3e  call    _CatDBSignalPendingJetFreezeOrStop
0x180019c43  mov     rcx, rbp; lpCriticalSection
0x180019c46  call    cs:__imp_LeaveCriticalSection
0x180019c4c  test    ebx, ebx
0x180019c4e  jnz     short loc_180019C58
0x180019c50  mov     ecx, edi; dwErrCode
0x180019c52  call    cs:__imp_SetLastError
0x180019c58  mov     eax, ebx
0x180019c5a  jmp     short loc_180019C7B
0x180019c5c  mov     ecx, 426h; dwErrCode
0x180019c61  call    cs:__imp_SetLastError
0x180019c67  xor     r9d, r9d; unsigned int
0x180019c6a  mov     [rsp+58h+var_38], esi; int
0x180019c6e  mov     r8d, 2006h; unsigned int
0x180019c74  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180019c79  xor     eax, eax
0x180019c7b  add     rsp, 38h
0x180019c7f  pop     rdi
0x180019c80  pop     rsi
0x180019c81  pop     rbp
0x180019c82  pop     rbx
0x180019c83  retn
```
