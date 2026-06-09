# _CatDBOpenJetThreadProc

- ea: `0x18001aa80`
- end: `0x18001ac5e`
- name: `_CatDBOpenJetThreadProc`
- size: `478`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800015b0`
- `0x180002b90`
- `0x18000a59c`
- `0x180019fe0`
- `0x18001aa80`
- `0x18001b620`
- `0x18001b670`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18001ac4e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18001ac4e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001aadc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ab64`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001aadc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ab64`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001aad3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001aad3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ab4f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001abb1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ac2d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ab4f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001abb1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ac2d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ab12`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001abd4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001abf1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ab12`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001abd4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001abf1`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x18001ac57`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x18001ac57`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001aaf3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ab87`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ac15`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001aaf3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ab87`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ac15`

## pseudocode

```c
void __fastcall __noreturn CatDBOpenJetThreadProc(_DWORD *Parameter)
{
  DWORD v2; // edx
  int v3; // edi
  unsigned int v4; // edx
  unsigned __int16 *v5; // rcx
  DWORD v6; // esi
  HANDLE v7; // rcx
  unsigned int v8; // edx
  unsigned __int16 *v9; // rcx
  unsigned int v10; // edx
  unsigned __int16 *v11; // rcx
  HMODULE v12; // rdi
  int v13; // [rsp+28h] [rbp-30h]

  if ( g_dwJetDBState == 3 && Parameter )
  {
    v2 = *Parameter;
    if ( *Parameter )
    {
      if ( g_hJetDBOpenThreadWaitEvent )
        WaitForSingleObject(g_hJetDBOpenThreadWaitEvent, v2);
      else
        ErrLog_LogError(0, v2, 0x1DFEu, 0x8000FFFF, 0, v13);
    }
    EnterCriticalSection(&g_JetDBOpenCS);
    v3 = 1;
    if ( g_hJetDBOpenThreadWaitEvent )
    {
      CloseHandle(g_hJetDBOpenThreadWaitEvent);
      g_hJetDBOpenThreadWaitEvent = 0;
    }
    if ( g_dwJetDBState == 3 )
    {
      g_dwJetDBState = 2;
      if ( !(unsigned int)CatDBSignalPendingJetFreezeOrStop() )
      {
        g_dwJetDBState = 4;
        LeaveCriticalSection(&g_JetDBOpenCS);
        v6 = CatDBInitJet(Parameter[4], 0);
        EnterCriticalSection(&g_JetDBOpenCS);
        g_fJetDBFirstPendingOpen = 0;
        CatDBSignalPendingJetOpen(v6);
        v7 = g_hJetDBOpenThread;
        if ( g_hJetDBOpenThread )
        {
          CloseHandle(g_hJetDBOpenThread);
          v7 = 0;
          g_hJetDBOpenThread = 0;
        }
        if ( v6 )
        {
          g_dwJetDBState = 2;
          CatDBSignalPendingJetFreezeOrStop();
          SetLastError(v6);
          ErrLog_LogError(v9, v8, 0x1E3Du, 0, 0, v13);
        }
        else
        {
          g_dwJetDBState = 1;
          if ( g_dwJetDBOpenRefCnt )
            goto LABEL_20;
          g_dwJetDBOpenRefCnt = 1;
          LeaveCriticalSection(&g_JetDBOpenCS);
          v3 = 0;
          _CatDBCloseJet(Parameter[4]);
        }
      }
    }
    else
    {
      SetLastError(0x8000FFFF);
      ErrLog_LogError(v5, v4, 0x1E11u, 0, 0, v13);
    }
  }
  else
  {
    v3 = 0;
    SetLastError(0x8000FFFF);
    ErrLog_LogError(v11, v10, 0x1DF7u, 0, 0, v13);
  }
  v7 = g_hJetDBOpenThread;
LABEL_20:
  if ( v7 )
  {
    CloseHandle(v7);
    g_hJetDBOpenThread = 0;
  }
  if ( v3 )
    LeaveCriticalSection(&g_JetDBOpenCS);
  if ( Parameter )
  {
    v12 = (HMODULE)*((_QWORD *)Parameter + 1);
    _CatDBFree(Parameter);
    if ( v12 )
      FreeLibraryAndExitThread(v12, 0);
  }
  ExitThread(0);
}

```

## disassembly

```asm
0x18001aa80  push    rbx
0x18001aa82  push    rsi
0x18001aa83  push    rdi
0x18001aa84  push    r14
0x18001aa86  sub     rsp, 38h
0x18001aa8a  cmp     cs:?g_dwJetDBState@@3KA, 3; ulong g_dwJetDBState
0x18001aa91  lea     r14, ?g_JetDBOpenCS@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_JetDBOpenCS
0x18001aa98  mov     rbx, rcx
0x18001aa9b  jnz     loc_18001ABEA
0x18001aaa1  test    rcx, rcx
0x18001aaa4  jz      loc_18001ABEA
0x18001aaaa  mov     edx, [rcx]; unsigned int
0x18001aaac  test    edx, edx
0x18001aaae  jz      short loc_18001AAD9
0x18001aab0  mov     rcx, cs:?g_hJetDBOpenThreadWaitEvent@@3PEAXEA; unsigned __int16 *
0x18001aab7  test    rcx, rcx
0x18001aaba  jnz     short loc_18001AAD3
0x18001aabc  mov     r9d, 8000FFFFh; unsigned int
0x18001aac2  mov     [rsp+58h+var_38], ecx; int
0x18001aac6  mov     r8d, 1DFEh; unsigned int
0x18001aacc  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001aad1  jmp     short loc_18001AAD9
0x18001aad3  call    cs:__imp_WaitForSingleObject
0x18001aad9  mov     rcx, r14; lpCriticalSection
0x18001aadc  call    cs:__imp_EnterCriticalSection
0x18001aae2  mov     rcx, cs:?g_hJetDBOpenThreadWaitEvent@@3PEAXEA; hObject
0x18001aae9  mov     edi, 1
0x18001aaee  test    rcx, rcx
0x18001aaf1  jz      short loc_18001AB04
0x18001aaf3  call    cs:__imp_CloseHandle
0x18001aaf9  mov     cs:?g_hJetDBOpenThreadWaitEvent@@3PEAXEA, 0; void * g_hJetDBOpenThreadWaitEvent
0x18001ab04  cmp     cs:?g_dwJetDBState@@3KA, 3; ulong g_dwJetDBState
0x18001ab0b  jz      short loc_18001AB2B
0x18001ab0d  mov     ecx, 8000FFFFh; dwErrCode
0x18001ab12  call    cs:__imp_SetLastError
0x18001ab18  mov     r8d, 1E11h
0x18001ab1e  mov     [rsp+58h+var_38], 0
0x18001ab26  jmp     loc_18001AC01
0x18001ab2b  mov     cs:?g_dwJetDBState@@3KA, 2; ulong g_dwJetDBState
0x18001ab35  call    _CatDBSignalPendingJetFreezeOrStop
0x18001ab3a  test    eax, eax
0x18001ab3c  jnz     loc_18001AC09
0x18001ab42  mov     rcx, r14; lpCriticalSection
0x18001ab45  mov     cs:?g_dwJetDBState@@3KA, 4; ulong g_dwJetDBState
0x18001ab4f  call    cs:__imp_LeaveCriticalSection
0x18001ab55  mov     ecx, [rbx+10h]
0x18001ab58  xor     edx, edx
0x18001ab5a  call    _CatDBInitJet
0x18001ab5f  mov     rcx, r14; lpCriticalSection
0x18001ab62  mov     esi, eax
0x18001ab64  call    cs:__imp_EnterCriticalSection
0x18001ab6a  mov     ecx, esi
0x18001ab6c  mov     cs:?g_fJetDBFirstPendingOpen@@3HA, 0; int g_fJetDBFirstPendingOpen
0x18001ab76  call    _CatDBSignalPendingJetOpen
0x18001ab7b  mov     rcx, cs:?g_hJetDBOpenThread@@3PEAXEA; hObject
0x18001ab82  test    rcx, rcx
0x18001ab85  jz      short loc_18001AB96
0x18001ab87  call    cs:__imp_CloseHandle
0x18001ab8d  xor     ecx, ecx
0x18001ab8f  mov     cs:?g_hJetDBOpenThread@@3PEAXEA, rcx; void * g_hJetDBOpenThread
0x18001ab96  test    esi, esi
0x18001ab98  jnz     short loc_18001ABC3
0x18001ab9a  cmp     cs:?g_dwJetDBOpenRefCnt@@3KA, esi; ulong g_dwJetDBOpenRefCnt
0x18001aba0  mov     cs:?g_dwJetDBState@@3KA, edi; ulong g_dwJetDBState
0x18001aba6  jnz     short loc_18001AC10
0x18001aba8  mov     rcx, r14; lpCriticalSection
0x18001abab  mov     cs:?g_dwJetDBOpenRefCnt@@3KA, edi; ulong g_dwJetDBOpenRefCnt
0x18001abb1  call    cs:__imp_LeaveCriticalSection
0x18001abb7  mov     ecx, [rbx+10h]; int
0x18001abba  xor     edi, edi
0x18001abbc  call    ?_CatDBCloseJet@@YAXH@Z; _CatDBCloseJet(int)
0x18001abc1  jmp     short loc_18001AC09
0x18001abc3  mov     cs:?g_dwJetDBState@@3KA, 2; ulong g_dwJetDBState
0x18001abcd  call    _CatDBSignalPendingJetFreezeOrStop
0x18001abd2  mov     ecx, esi; dwErrCode
0x18001abd4  call    cs:__imp_SetLastError
0x18001abda  mov     r8d, 1E3Dh
0x18001abe0  mov     [rsp+58h+var_38], 0
0x18001abe8  jmp     short loc_18001AC01
0x18001abea  xor     edi, edi
0x18001abec  mov     ecx, 8000FFFFh; dwErrCode
0x18001abf1  call    cs:__imp_SetLastError
0x18001abf7  mov     r8d, 1DF7h; unsigned int
0x18001abfd  mov     [rsp+58h+var_38], edi; int
0x18001ac01  xor     r9d, r9d; unsigned int
0x18001ac04  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001ac09  mov     rcx, cs:?g_hJetDBOpenThread@@3PEAXEA; hObject
0x18001ac10  test    rcx, rcx
0x18001ac13  jz      short loc_18001AC26
0x18001ac15  call    cs:__imp_CloseHandle
0x18001ac1b  mov     cs:?g_hJetDBOpenThread@@3PEAXEA, 0; void * g_hJetDBOpenThread
0x18001ac26  test    edi, edi
0x18001ac28  jz      short loc_18001AC33
0x18001ac2a  mov     rcx, r14; lpCriticalSection
0x18001ac2d  call    cs:__imp_LeaveCriticalSection
0x18001ac33  test    rbx, rbx
0x18001ac36  jz      short loc_18001AC55
0x18001ac38  mov     rdi, [rbx+8]
0x18001ac3c  mov     rcx, rbx; void *
0x18001ac3f  call    ?_CatDBFree@@YAXPEAX@Z; _CatDBFree(void *)
0x18001ac44  test    rdi, rdi
0x18001ac47  jz      short loc_18001AC55
0x18001ac49  xor     edx, edx; dwExitCode
0x18001ac4b  mov     rcx, rdi; hLibModule
0x18001ac4e  call    cs:__imp_FreeLibraryAndExitThread
0x18001ac54  int     3; Trap to Debugger
0x18001ac55  xor     ecx, ecx; dwExitCode
0x18001ac57  call    cs:__imp_ExitThread
```
