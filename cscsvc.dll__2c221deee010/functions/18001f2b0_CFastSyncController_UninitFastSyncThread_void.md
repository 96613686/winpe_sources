# CFastSyncController::_UninitFastSyncThread(void)

- ea: `0x18001f2b0`
- end: `0x18001f52e`
- name: `?_UninitFastSyncThread@CFastSyncController@@AEAAXXZ`
- size: `638`
- prototype: `void __fastcall(CFastSyncController *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180034990`

## callees

- `0x18001f2b0`
- `0x18002f10c`
- `0x180036394`
- `0x180069038`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18001f305`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18001f3bc`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18001f305`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18001f3bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f3f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f458`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f4a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f4c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f504`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f3f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f458`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f4a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f4c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f504`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18001f3ed`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18001f450`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18001f49e`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18001f4bf`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18001f3ed`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18001f450`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18001f49e`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18001f4bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001f2d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001f391`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001f3e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001f447`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001f495`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001f4b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001f2d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001f391`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001f3e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001f447`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001f495`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001f4b6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f353`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f353`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001f363`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001f363`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f36d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f36d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001f2c7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001f2c7`

## pseudocode

```c
void __fastcall CFastSyncController::_UninitFastSyncThread(CFastSyncController *this)
{
  HANDLE CurrentThread; // rbp
  CObjectMonitor *v3; // rax
  __int64 v4; // rbx
  HANDLE v6; // rbp
  HANDLE v7; // rax
  int v8; // ebx
  DWORD v9; // eax
  HANDLE v10; // rax
  int ThreadPriority; // ebx
  DWORD CurrentThreadId; // eax
  HANDLE v13; // rax
  HANDLE v14; // rax
  int v15; // ebx
  DWORD v16; // eax
  DWORD v17; // eax
  int v18; // [rsp+28h] [rbp-10h]
  char v19; // [rsp+28h] [rbp-10h]
  char v20; // [rsp+28h] [rbp-10h]

  CoUninitialize();
  if ( *((_DWORD *)this + 7) )
  {
    CurrentThread = GetCurrentThread();
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      v10 = GetCurrentThread();
      ThreadPriority = GetThreadPriority(v10);
      CurrentThreadId = GetCurrentThreadId();
      v19 = 89;
      WPP_SF_DDc(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        107,
        WPP_7967f24143133d59f1b33f7a742017bc_Traceguids,
        CurrentThreadId,
        ThreadPriority,
        v19);
    }
    if ( !SetThreadPriority(CurrentThread, 0x20000) )
      ResultFromLastError();
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0 )
      {
LABEL_9:
        if ( v3 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 0x20) != 0 )
        {
          v17 = GetCurrentThreadId();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 113, WPP_7967f24143133d59f1b33f7a742017bc_Traceguids, v17);
        }
        goto LABEL_12;
      }
      v13 = GetCurrentThread();
      v8 = GetThreadPriority(v13);
      v9 = GetCurrentThreadId();
      LOBYTE(v18) = 89;
LABEL_25:
      WPP_SF_DDc(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, WPP_7967f24143133d59f1b33f7a742017bc_Traceguids, v9, v8, v18);
      v3 = WPP_GLOBAL_Control;
      goto LABEL_9;
    }
  }
  else
  {
    v6 = GetCurrentThread();
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      v14 = GetCurrentThread();
      v15 = GetThreadPriority(v14);
      v16 = GetCurrentThreadId();
      v20 = 78;
      WPP_SF_DDc(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        107,
        WPP_7967f24143133d59f1b33f7a742017bc_Traceguids,
        v16,
        v15,
        v20);
    }
    if ( !SetThreadPriority(v6, 0) )
      ResultFromLastError();
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0 )
        goto LABEL_9;
      v7 = GetCurrentThread();
      v8 = GetThreadPriority(v7);
      v9 = GetCurrentThreadId();
      LOBYTE(v18) = 78;
      goto LABEL_25;
    }
  }
LABEL_12:
  v4 = *((_QWORD *)this + 4);
  if ( v4 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v4 + 8));
    EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 32));
    if ( (*(_DWORD *)(v4 + 24))-- == 1 )
      SetEvent(*(HANDLE *)(v4 + 16));
    LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 32));
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 8), 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(__int64, __int64))v4)(v4, 1);
  }
}

```

## disassembly

```asm
0x18001f2b0  mov     [rsp+arg_18], rbx
0x18001f2b5  push    rdi
0x18001f2b6  sub     rsp, 30h
0x18001f2ba  mov     [rsp+38h+arg_8], rbp
0x18001f2bf  mov     rdi, rcx
0x18001f2c2  mov     [rsp+38h+arg_10], rsi
0x18001f2c7  call    cs:__imp_CoUninitialize
0x18001f2cd  cmp     dword ptr [rdi+1Ch], 0
0x18001f2d1  jz      loc_18001F391
0x18001f2d7  call    cs:__imp_GetCurrentThread
0x18001f2dd  mov     rbp, rax
0x18001f2e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f2e7  lea     rsi, WPP_GLOBAL_Control
0x18001f2ee  cmp     rcx, rsi
0x18001f2f1  jz      short loc_18001F2FD
0x18001f2f3  test    byte ptr [rcx+1Ch], 20h
0x18001f2f7  jnz     loc_18001F447
0x18001f2fd  mov     edx, 20000h; nPriority
0x18001f302  mov     rcx, rbp; hThread
0x18001f305  call    cs:__imp_SetThreadPriority
0x18001f30b  test    eax, eax
0x18001f30d  jz      loc_18001F48B
0x18001f313  mov     rax, cs:WPP_GLOBAL_Control
0x18001f31a  cmp     rax, rsi
0x18001f31d  jz      short loc_18001F338
0x18001f31f  test    byte ptr [rax+1Ch], 20h
0x18001f323  jnz     loc_18001F495
0x18001f329  cmp     rax, rsi
0x18001f32c  jz      short loc_18001F338
0x18001f32e  test    byte ptr [rax+1Ch], 20h
0x18001f332  jnz     loc_18001F504
0x18001f338  mov     rbx, [rdi+20h]
0x18001f33c  mov     rsi, [rsp+38h+arg_10]
0x18001f341  mov     rbp, [rsp+38h+arg_8]
0x18001f346  test    rbx, rbx
0x18001f349  jz      short loc_18001F386
0x18001f34b  lock inc dword ptr [rbx+8]
0x18001f34f  lea     rcx, [rbx+20h]; lpCriticalSection
0x18001f353  call    cs:__imp_EnterCriticalSection
0x18001f359  sub     dword ptr [rbx+18h], 1
0x18001f35d  jnz     short loc_18001F369
0x18001f35f  mov     rcx, [rbx+10h]; hEvent
0x18001f363  call    cs:__imp_SetEvent
0x18001f369  lea     rcx, [rbx+20h]; lpCriticalSection
0x18001f36d  call    cs:__imp_LeaveCriticalSection
0x18001f373  mov     eax, 0FFFFFFFFh
0x18001f378  lock xadd [rbx+8], eax
0x18001f37d  cmp     eax, 1
0x18001f380  jz      loc_18001F42F
0x18001f386  mov     rbx, [rsp+38h+arg_18]
0x18001f38b  add     rsp, 30h
0x18001f38f  pop     rdi
0x18001f390  retn
0x18001f391  call    cs:__imp_GetCurrentThread
0x18001f397  mov     rbp, rax
0x18001f39a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f3a1  lea     rsi, WPP_GLOBAL_Control
0x18001f3a8  cmp     rcx, rsi
0x18001f3ab  jz      short loc_18001F3B7
0x18001f3ad  test    byte ptr [rcx+1Ch], 20h
0x18001f3b1  jnz     loc_18001F4B6
0x18001f3b7  xor     edx, edx; nPriority
0x18001f3b9  mov     rcx, rbp; hThread
0x18001f3bc  call    cs:__imp_SetThreadPriority
0x18001f3c2  test    eax, eax
0x18001f3c4  jz      loc_18001F4FA
0x18001f3ca  mov     rax, cs:WPP_GLOBAL_Control
0x18001f3d1  cmp     rax, rsi
0x18001f3d4  jz      loc_18001F338
0x18001f3da  test    byte ptr [rax+1Ch], 20h
0x18001f3de  jz      loc_18001F329
0x18001f3e4  call    cs:__imp_GetCurrentThread
0x18001f3ea  mov     rcx, rax; hThread
0x18001f3ed  call    cs:__imp_GetThreadPriority
0x18001f3f3  mov     ebx, eax
0x18001f3f5  call    cs:__imp_GetCurrentThreadId
0x18001f3fb  mov     byte ptr [rsp+38h+var_10], 4Eh ; 'N'
0x18001f400  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f407  lea     r8, WPP_7967f24143133d59f1b33f7a742017bc_Traceguids
0x18001f40e  mov     r9d, eax
0x18001f411  mov     [rsp+38h+var_18], ebx
0x18001f415  mov     edx, 6Ch ; 'l'
0x18001f41a  mov     rcx, [rcx+10h]
0x18001f41e  call    WPP_SF_DDc
0x18001f423  mov     rax, cs:WPP_GLOBAL_Control
0x18001f42a  jmp     loc_18001F329
0x18001f42f  mov     rax, [rbx]
0x18001f432  mov     edx, 1
0x18001f437  mov     rcx, rbx
0x18001f43a  mov     rax, [rax]
0x18001f43d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f442  jmp     loc_18001F386
0x18001f447  call    cs:__imp_GetCurrentThread
0x18001f44d  mov     rcx, rax; hThread
0x18001f450  call    cs:__imp_GetThreadPriority
0x18001f456  mov     ebx, eax
0x18001f458  call    cs:__imp_GetCurrentThreadId
0x18001f45e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f465  lea     r8, WPP_7967f24143133d59f1b33f7a742017bc_Traceguids
0x18001f46c  mov     edx, 6Bh ; 'k'
0x18001f471  mov     byte ptr [rsp+38h+var_10], 59h ; 'Y'
0x18001f476  mov     r9d, eax
0x18001f479  mov     [rsp+38h+var_18], ebx
0x18001f47d  mov     rcx, [rcx+10h]
0x18001f481  call    WPP_SF_DDc
0x18001f486  jmp     loc_18001F2FD
0x18001f48b  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18001f490  jmp     loc_18001F313
0x18001f495  call    cs:__imp_GetCurrentThread
0x18001f49b  mov     rcx, rax; hThread
0x18001f49e  call    cs:__imp_GetThreadPriority
0x18001f4a4  mov     ebx, eax
0x18001f4a6  call    cs:__imp_GetCurrentThreadId
0x18001f4ac  mov     byte ptr [rsp+38h+var_10], 59h ; 'Y'
0x18001f4b1  jmp     loc_18001F400
0x18001f4b6  call    cs:__imp_GetCurrentThread
0x18001f4bc  mov     rcx, rax; hThread
0x18001f4bf  call    cs:__imp_GetThreadPriority
0x18001f4c5  mov     ebx, eax
0x18001f4c7  call    cs:__imp_GetCurrentThreadId
0x18001f4cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f4d4  lea     r8, WPP_7967f24143133d59f1b33f7a742017bc_Traceguids
0x18001f4db  mov     edx, 6Bh ; 'k'
0x18001f4e0  mov     byte ptr [rsp+38h+var_10], 4Eh ; 'N'
0x18001f4e5  mov     r9d, eax
0x18001f4e8  mov     [rsp+38h+var_18], ebx
0x18001f4ec  mov     rcx, [rcx+10h]
0x18001f4f0  call    WPP_SF_DDc
0x18001f4f5  jmp     loc_18001F3B7
0x18001f4fa  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18001f4ff  jmp     loc_18001F3CA
0x18001f504  call    cs:__imp_GetCurrentThreadId
0x18001f50a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f511  lea     r8, WPP_7967f24143133d59f1b33f7a742017bc_Traceguids
0x18001f518  mov     edx, 71h ; 'q'
0x18001f51d  mov     r9d, eax
0x18001f520  mov     rcx, [rcx+10h]
0x18001f524  call    WPP_SF_d
0x18001f529  jmp     loc_18001F338
```
