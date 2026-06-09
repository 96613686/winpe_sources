# StartAsyncMachine

- ea: `0x180080b2c`
- end: `0x180081088`
- name: `StartAsyncMachine`
- size: `1372`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180001544`
- `0x180029cd0`

## callees

- `0x18004e580`
- `0x18004e984`
- `0x18007fe30`
- `0x18008060c`
- `0x1800806c4`
- `0x180080868`
- `0x180080b2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180080c20`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180080c7d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180080cd7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180080c20`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180080c7d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180080cd7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180080d3b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180080d3b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180081039`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180081039`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180080c41`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180080c41`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180080f3b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180080f3b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180080df9`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180080df9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180080e94`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180080e94`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180080f9b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180080f9b`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180080ee7`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180080ee7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080c2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080c8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080ce9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080d9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080e0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080e9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080ef1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080f45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080fb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080c2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080c8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080ce9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080d9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080e0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080e9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080ef1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080f45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080fb7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180080f86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180080fa8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180080ffa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180080f86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180080fa8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180080ffa`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180081021`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180081021`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180080d91`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180080d91`

## string_xrefs

- `0x180080d8a`: `rasapi32.dll`

## pseudocode

```c
DWORD __fastcall StartAsyncMachine(__int64 a1, __int64 a2, void *a3)
{
  HANDLE EventW; // rax
  __int64 v8; // rcx
  HANDLE *v9; // rax
  DWORD v10; // eax
  DWORD v11; // edi
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  DWORD LastError; // eax
  BOOL v16; // ebx
  void *v17; // rcx
  DWORD ThreadId; // [rsp+60h] [rbp+8h] BYREF
  void *DuplicateTokenHandle; // [rsp+68h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, WPP_a844d46fc5703f471860e34880cece0e_Traceguids);
  }
  ThreadId = 0;
  *(_DWORD *)(a1 + 88) = 2;
  *(_DWORD *)(a1 + 192) = 2;
  *(_DWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_DWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = -1;
  *(_DWORD *)(a1 + 136) = 1;
  *(_QWORD *)(a1 + 144) = a1;
  *(_QWORD *)(a1 + 152) = a2;
  *(_QWORD *)(a1 + 200) = a1;
  *(_QWORD *)(a1 + 208) = a2;
  *(_DWORD *)(a1 + 248) = 3;
  *(_QWORD *)(a1 + 256) = a1;
  *(_QWORD *)(a1 + 264) = a2;
  *(_DWORD *)(a1 + 304) = 4;
  *(_QWORD *)(a1 + 312) = a1;
  *(_QWORD *)(a1 + 320) = a2;
  *(_QWORD *)(a1 + 96) = a2;
  EventW = CreateEventW(0, 0, 0, 0);
  *(_QWORD *)(a1 + 64) = EventW;
  if ( !EventW )
    return GetLastError();
  EnterCriticalSection(&csAsyncLock);
  InsertAsyncWorkItem(a1);
  if ( hAsyncThread )
  {
    v11 = 0;
    if ( a3 )
    {
      DuplicateTokenHandle = 0;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, WPP_a844d46fc5703f471860e34880cece0e_Traceguids);
      }
      if ( !NtCurrentTeb()->IsImpersonating || RevertToSelf() )
      {
        if ( DuplicateToken(a3, SecurityImpersonation, &DuplicateTokenHandle) )
        {
          if ( !SetThreadToken(&hAsyncThread, DuplicateTokenHandle) )
          {
            LastError = GetLastError();
            v11 = LastError;
            if ( LastError
              && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                88,
                WPP_a844d46fc5703f471860e34880cece0e_Traceguids,
                LastError);
            }
            CloseHandle(DuplicateTokenHandle);
            if ( !v11 )
              goto LABEL_76;
            goto LABEL_72;
          }
          v16 = ImpersonateLoggedOnUser(DuplicateTokenHandle);
          CloseHandle(DuplicateTokenHandle);
          DuplicateTokenHandle = 0;
          if ( !v16 )
          {
            v10 = GetLastError();
            v11 = v10;
            if ( v10 )
            {
              v12 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_72;
              }
              v13 = 89;
              goto LABEL_71;
            }
          }
        }
        else
        {
          v10 = GetLastError();
          v11 = v10;
          if ( v10 )
          {
            v12 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_72;
            }
            v13 = 87;
            goto LABEL_71;
          }
        }
      }
      else
      {
        v10 = GetLastError();
        v11 = v10;
        if ( v10 )
        {
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_72;
          }
          v13 = 86;
          goto LABEL_71;
        }
      }
    }
  }
  else
  {
    v8 = 16;
    v9 = &hDMEvent;
    do
    {
      *(_BYTE *)v9 = 0;
      v9 = (HANDLE *)((char *)v9 + 1);
      --v8;
    }
    while ( v8 );
    qword_1800FDD98 = (__int64)CreateEventW(0, 0, 0, 0);
    if ( qword_1800FDD98 )
    {
      hDMEvent = CreateEventW(0, 0, 0, 0);
      if ( hDMEvent )
      {
        dword_1800FFB60 = 5;
        WaitForSingleObject(HEventNotHangingUp, 0xFFFFFFFF);
        v10 = InitializeContextQueue(v14, qword_1800FDD98);
        v11 = v10;
        if ( v10 )
        {
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_72;
          }
          v13 = 82;
          goto LABEL_71;
        }
        if ( GetModuleHandleExW(0, L"rasapi32.dll", &g_hModule) )
        {
          hAsyncThread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)AsyncMachineWorker, a3, 0, &ThreadId);
          if ( !hAsyncThread )
          {
            v10 = GetLastError();
            v11 = v10;
            if ( v10 )
            {
              v12 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_72;
              }
              v13 = 84;
              goto LABEL_71;
            }
          }
        }
        else
        {
          v10 = GetLastError();
          v11 = v10;
          if ( v10 )
          {
            v12 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_72;
            }
            v13 = 83;
            goto LABEL_71;
          }
        }
      }
      else
      {
        v10 = GetLastError();
        v11 = v10;
        if ( v10 )
        {
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_72;
          }
          v13 = 81;
          goto LABEL_71;
        }
      }
    }
    else
    {
      v10 = GetLastError();
      v11 = v10;
      if ( v10 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_72;
        }
        v13 = 80;
LABEL_71:
        WPP_SF_d(v12[2], v13, WPP_a844d46fc5703f471860e34880cece0e_Traceguids, v10);
LABEL_72:
        v17 = *(void **)(a1 + 64);
        if ( v17 )
        {
          CloseHandle(v17);
          *(_QWORD *)(a1 + 64) = 0;
        }
        RemoveAsyncWorkItem(a1);
        CleanUpDMEvent();
        if ( g_hModule )
        {
          FreeLibrary(g_hModule);
          g_hModule = 0;
        }
      }
    }
  }
LABEL_76:
  LeaveCriticalSection(&csAsyncLock);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, WPP_a844d46fc5703f471860e34880cece0e_Traceguids, v11);
  }
  return v11;
}

```

## disassembly

```asm
0x180080b2c  mov     [rsp+arg_10], rbx
0x180080b31  mov     [rsp+arg_18], rbp
0x180080b36  push    rsi
0x180080b37  push    rdi
0x180080b38  push    r12
0x180080b3a  push    r13
0x180080b3c  push    r15
0x180080b3e  sub     rsp, 30h
0x180080b42  mov     rbp, r8
0x180080b45  mov     rbx, rdx
0x180080b48  mov     rsi, rcx
0x180080b4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180080b52  lea     r13, WPP_GLOBAL_Control
0x180080b59  mov     r12d, 800h
0x180080b5f  cmp     rcx, r13
0x180080b62  jz      short loc_180080B85
0x180080b64  test    [rcx+1Ch], r12d
0x180080b68  jz      short loc_180080B85
0x180080b6a  cmp     byte ptr [rcx+19h], 6
0x180080b6e  jb      short loc_180080B85
0x180080b70  mov     rcx, [rcx+10h]
0x180080b74  lea     r8, WPP_a844d46fc5703f471860e34880cece0e_Traceguids
0x180080b7b  mov     edx, 4Fh ; 'O'
0x180080b80  call    WPP_SF_
0x180080b85  mov     r15d, 2
0x180080b8b  mov     [rsp+58h+ThreadId], 0
0x180080b93  xor     r9d, r9d; lpName
0x180080b96  mov     [rsi+58h], r15d
0x180080b9a  xor     r8d, r8d; bInitialState
0x180080b9d  mov     [rsi+0C0h], r15d
0x180080ba4  xor     edx, edx; bManualReset
0x180080ba6  mov     dword ptr [rsi+38h], 0
0x180080bad  xor     ecx, ecx; lpEventAttributes
0x180080baf  mov     qword ptr [rsi+40h], 0
0x180080bb7  mov     dword ptr [rsi+48h], 0
0x180080bbe  mov     qword ptr [rsi+50h], 0FFFFFFFFFFFFFFFFh
0x180080bc6  mov     dword ptr [rsi+88h], 1
0x180080bd0  mov     [rsi+90h], rsi
0x180080bd7  mov     [rsi+98h], rbx
0x180080bde  mov     [rsi+0C8h], rsi
0x180080be5  mov     [rsi+0D0h], rbx
0x180080bec  mov     dword ptr [rsi+0F8h], 3
0x180080bf6  mov     [rsi+100h], rsi
0x180080bfd  mov     [rsi+108h], rbx
0x180080c04  mov     dword ptr [rsi+130h], 4
0x180080c0e  mov     [rsi+138h], rsi
0x180080c15  mov     [rsi+140h], rbx
0x180080c1c  mov     [rsi+60h], rbx
0x180080c20  call    cs:__imp_CreateEventW
0x180080c26  mov     [rsi+40h], rax
0x180080c2a  test    rax, rax
0x180080c2d  jnz     short loc_180080C3A
0x180080c2f  call    cs:__imp_GetLastError
0x180080c35  jmp     loc_180081071
0x180080c3a  lea     rcx, csAsyncLock; lpCriticalSection
0x180080c41  call    cs:__imp_EnterCriticalSection
0x180080c47  mov     rcx, rsi
0x180080c4a  call    InsertAsyncWorkItem
0x180080c4f  cmp     cs:hAsyncThread, 0
0x180080c57  jnz     loc_180080E4D
0x180080c5d  mov     ecx, 10h
0x180080c62  lea     rax, hDMEvent
0x180080c69  mov     byte ptr [rax], 0
0x180080c6c  inc     rax
0x180080c6f  sub     rcx, 1; lpEventAttributes
0x180080c73  jnz     short loc_180080C69
0x180080c75  xor     r9d, r9d; lpName
0x180080c78  xor     r8d, r8d; bInitialState
0x180080c7b  xor     edx, edx; bManualReset
0x180080c7d  call    cs:__imp_CreateEventW
0x180080c83  mov     cs:qword_1800FDD98, rax
0x180080c8a  test    rax, rax
0x180080c8d  jnz     short loc_180080CCD
0x180080c8f  call    cs:__imp_GetLastError
0x180080c95  mov     edi, eax
0x180080c97  test    eax, eax
0x180080c99  jz      loc_180081032
0x180080c9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180080ca6  cmp     rcx, r13
0x180080ca9  jz      loc_180080FF1
0x180080caf  test    [rcx+1Ch], r12d
0x180080cb3  jz      loc_180080FF1
0x180080cb9  cmp     [rcx+19h], r15b
0x180080cbd  jb      loc_180080FF1
0x180080cc3  mov     edx, 50h ; 'P'
0x180080cc8  jmp     loc_180080FDE
0x180080ccd  xor     r9d, r9d; lpName
0x180080cd0  xor     r8d, r8d; bInitialState
0x180080cd3  xor     edx, edx; bManualReset
0x180080cd5  xor     ecx, ecx; lpEventAttributes
0x180080cd7  call    cs:__imp_CreateEventW
0x180080cdd  mov     cs:hDMEvent, rax
0x180080ce4  test    rax, rax
0x180080ce7  jnz     short loc_180080D27
0x180080ce9  call    cs:__imp_GetLastError
0x180080cef  mov     edi, eax
0x180080cf1  test    eax, eax
0x180080cf3  jz      loc_180081032
0x180080cf9  mov     rcx, cs:WPP_GLOBAL_Control
0x180080d00  cmp     rcx, r13
0x180080d03  jz      loc_180080FF1
0x180080d09  test    [rcx+1Ch], r12d
0x180080d0d  jz      loc_180080FF1
0x180080d13  cmp     [rcx+19h], r15b
0x180080d17  jb      loc_180080FF1
0x180080d1d  mov     edx, 51h ; 'Q'
0x180080d22  jmp     loc_180080FDE
0x180080d27  mov     rcx, cs:HEventNotHangingUp; hHandle
0x180080d2e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180080d31  mov     cs:dword_1800FFB60, 5
0x180080d3b  call    cs:__imp_WaitForSingleObject
0x180080d41  mov     rdx, cs:qword_1800FDD98
0x180080d48  call    InitializeContextQueue
0x180080d4d  mov     edi, eax
0x180080d4f  test    eax, eax
0x180080d51  jz      short loc_180080D81
0x180080d53  mov     rcx, cs:WPP_GLOBAL_Control
0x180080d5a  cmp     rcx, r13
0x180080d5d  jz      loc_180080FF1
0x180080d63  test    [rcx+1Ch], r12d
0x180080d67  jz      loc_180080FF1
0x180080d6d  cmp     [rcx+19h], r15b
0x180080d71  jb      loc_180080FF1
0x180080d77  mov     edx, 52h ; 'R'
0x180080d7c  jmp     loc_180080FDE
0x180080d81  lea     r8, g_hModule; phModule
0x180080d88  xor     ecx, ecx; dwFlags
0x180080d8a  lea     rdx, aRasapi32Dll_0; "rasapi32.dll"
0x180080d91  call    cs:__imp_GetModuleHandleExW
0x180080d97  test    eax, eax
0x180080d99  jnz     short loc_180080DD9
0x180080d9b  call    cs:__imp_GetLastError
0x180080da1  mov     edi, eax
0x180080da3  test    eax, eax
0x180080da5  jz      loc_180081032
0x180080dab  mov     rcx, cs:WPP_GLOBAL_Control
0x180080db2  cmp     rcx, r13
0x180080db5  jz      loc_180080FF1
0x180080dbb  test    [rcx+1Ch], r12d
0x180080dbf  jz      loc_180080FF1
0x180080dc5  cmp     [rcx+19h], r15b
0x180080dc9  jb      loc_180080FF1
0x180080dcf  mov     edx, 53h ; 'S'
0x180080dd4  jmp     loc_180080FDE
0x180080dd9  lea     rax, [rsp+58h+ThreadId]
0x180080dde  mov     r9, rbp; lpParameter
0x180080de1  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x180080de6  lea     r8, AsyncMachineWorker; lpStartAddress
0x180080ded  xor     edx, edx; dwStackSize
0x180080def  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x180080df7  xor     ecx, ecx; lpThreadAttributes
0x180080df9  call    cs:__imp_CreateThread
0x180080dff  mov     cs:hAsyncThread, rax
0x180080e06  test    rax, rax
0x180080e09  jnz     loc_180081032
0x180080e0f  call    cs:__imp_GetLastError
0x180080e15  mov     edi, eax
0x180080e17  test    eax, eax
0x180080e19  jz      loc_180081032
0x180080e1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180080e26  cmp     rcx, r13
0x180080e29  jz      loc_180080FF1
0x180080e2f  test    [rcx+1Ch], r12d
0x180080e33  jz      loc_180080FF1
0x180080e39  cmp     [rcx+19h], r15b
0x180080e3d  jb      loc_180080FF1
0x180080e43  mov     edx, 54h ; 'T'
0x180080e48  jmp     loc_180080FDE
0x180080e4d  xor     edi, edi
0x180080e4f  test    rbp, rbp
0x180080e52  jz      loc_180081032
0x180080e58  mov     [rsp+58h+DuplicateTokenHandle], rdi
0x180080e5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180080e64  cmp     rcx, r13
0x180080e67  jz      short loc_180080E88
0x180080e69  test    [rcx+1Ch], r12d
0x180080e6d  jz      short loc_180080E88
0x180080e6f  cmp     byte ptr [rcx+19h], 5
0x180080e73  jb      short loc_180080E88
0x180080e75  mov     rcx, [rcx+10h]
0x180080e79  lea     edx, [rdi+55h]
0x180080e7c  lea     r8, WPP_a844d46fc5703f471860e34880cece0e_Traceguids
0x180080e83  call    WPP_SF_
0x180080e88  mov     eax, gs:179Ch
0x180080e90  test    eax, eax
0x180080e92  jz      short loc_180080EDC
0x180080e94  call    cs:__imp_RevertToSelf
0x180080e9a  test    eax, eax
0x180080e9c  jnz     short loc_180080EDC
0x180080e9e  call    cs:__imp_GetLastError
0x180080ea4  mov     edi, eax
0x180080ea6  test    eax, eax
0x180080ea8  jz      loc_180081032
0x180080eae  mov     rcx, cs:WPP_GLOBAL_Control
0x180080eb5  cmp     rcx, r13
0x180080eb8  jz      loc_180080FF1
0x180080ebe  test    [rcx+1Ch], r12d
0x180080ec2  jz      loc_180080FF1
0x180080ec8  cmp     [rcx+19h], r15b
0x180080ecc  jb      loc_180080FF1
0x180080ed2  mov     edx, 56h ; 'V'
0x180080ed7  jmp     loc_180080FDE
0x180080edc  lea     r8, [rsp+58h+DuplicateTokenHandle]; DuplicateTokenHandle
0x180080ee1  mov     edx, r15d; ImpersonationLevel
0x180080ee4  mov     rcx, rbp; ExistingTokenHandle
0x180080ee7  call    cs:__imp_DuplicateToken
0x180080eed  test    eax, eax
0x180080eef  jnz     short loc_180080F2F
0x180080ef1  call    cs:__imp_GetLastError
0x180080ef7  mov     edi, eax
0x180080ef9  test    eax, eax
0x180080efb  jz      loc_180081032
0x180080f01  mov     rcx, cs:WPP_GLOBAL_Control
0x180080f08  cmp     rcx, r13
0x180080f0b  jz      loc_180080FF1
0x180080f11  test    [rcx+1Ch], r12d
0x180080f15  jz      loc_180080FF1
0x180080f1b  cmp     [rcx+19h], r15b
0x180080f1f  jb      loc_180080FF1
0x180080f25  mov     edx, 57h ; 'W'
0x180080f2a  jmp     loc_180080FDE
0x180080f2f  mov     rdx, [rsp+58h+DuplicateTokenHandle]; Token
0x180080f34  lea     rcx, hAsyncThread; Thread
0x180080f3b  call    cs:__imp_SetThreadToken
0x180080f41  test    eax, eax
0x180080f43  jnz     short loc_180080F96
0x180080f45  call    cs:__imp_GetLastError
0x180080f4b  mov     edi, eax
0x180080f4d  test    eax, eax
0x180080f4f  jz      short loc_180080F81
0x180080f51  mov     rcx, cs:WPP_GLOBAL_Control
0x180080f58  cmp     rcx, r13
0x180080f5b  jz      short loc_180080F81
0x180080f5d  test    [rcx+1Ch], r12d
0x180080f61  jz      short loc_180080F81
0x180080f63  cmp     [rcx+19h], r15b
0x180080f67  jb      short loc_180080F81
0x180080f69  mov     rcx, [rcx+10h]
0x180080f6d  lea     r8, WPP_a844d46fc5703f471860e34880cece0e_Traceguids
0x180080f74  mov     edx, 58h ; 'X'
0x180080f79  mov     r9d, eax
0x180080f7c  call    WPP_SF_d
0x180080f81  mov     rcx, [rsp+58h+DuplicateTokenHandle]; hObject
0x180080f86  call    cs:__imp_CloseHandle
0x180080f8c  test    edi, edi
0x180080f8e  jz      loc_180081032
0x180080f94  jmp     short loc_180080FF1
0x180080f96  mov     rcx, [rsp+58h+DuplicateTokenHandle]; hToken
0x180080f9b  call    cs:__imp_ImpersonateLoggedOnUser
0x180080fa1  mov     rcx, [rsp+58h+DuplicateTokenHandle]; hObject
0x180080fa6  mov     ebx, eax
0x180080fa8  call    cs:__imp_CloseHandle
0x180080fae  mov     [rsp+58h+DuplicateTokenHandle], rdi
0x180080fb3  test    ebx, ebx
0x180080fb5  jnz     short loc_180081032
0x180080fb7  call    cs:__imp_GetLastError
0x180080fbd  mov     edi, eax
0x180080fbf  test    eax, eax
0x180080fc1  jz      short loc_180081032
0x180080fc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180080fca  cmp     rcx, r13
0x180080fcd  jz      short loc_180080FF1
0x180080fcf  test    [rcx+1Ch], r12d
0x180080fd3  jz      short loc_180080FF1
0x180080fd5  cmp     [rcx+19h], r15b
0x180080fd9  jb      short loc_180080FF1
0x180080fdb  lea     edx, [rbx+59h]
0x180080fde  mov     rcx, [rcx+10h]
0x180080fe2  lea     r8, WPP_a844d46fc5703f471860e34880cece0e_Traceguids
0x180080fe9  mov     r9d, eax
0x180080fec  call    WPP_SF_d
0x180080ff1  mov     rcx, [rsi+40h]; hObject
0x180080ff5  test    rcx, rcx
0x180080ff8  jz      short loc_180081008
0x180080ffa  call    cs:__imp_CloseHandle
0x180081000  mov     qword ptr [rsi+40h], 0
0x180081008  mov     rcx, rsi
0x18008100b  call    RemoveAsyncWorkItem
0x180081010  call    CleanUpDMEvent
0x180081015  mov     rcx, cs:g_hModule; hLibModule
0x18008101c  test    rcx, rcx
0x18008101f  jz      short loc_180081032
0x180081021  call    cs:__imp_FreeLibrary
0x180081027  mov     cs:g_hModule, 0
0x180081032  lea     rcx, csAsyncLock; lpCriticalSection
0x180081039  call    cs:__imp_LeaveCriticalSection
0x18008103f  mov     rcx, cs:WPP_GLOBAL_Control
0x180081046  cmp     rcx, r13
0x180081049  jz      short loc_18008106F
0x18008104b  test    [rcx+1Ch], r12d
0x18008104f  jz      short loc_18008106F
0x180081051  cmp     byte ptr [rcx+19h], 6
0x180081055  jb      short loc_18008106F
0x180081057  mov     rcx, [rcx+10h]
0x18008105b  lea     r8, WPP_a844d46fc5703f471860e34880cece0e_Traceguids
0x180081062  mov     edx, 5Ah ; 'Z'
0x180081067  mov     r9d, edi
0x18008106a  call    WPP_SF_d
0x18008106f  mov     eax, edi
0x180081071  mov     rbx, [rsp+58h+arg_10]
  ... truncated ...
```
