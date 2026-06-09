# CFastSyncController::_PrepForSyncThreadUninitCallback(__int64)

- ea: `0x18001d1d0`
- end: `0x18001d47b`
- name: `?_PrepForSyncThreadUninitCallback@CFastSyncController@@CAX_J@Z`
- size: `683`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18001d1d0`
- `0x18002f10c`
- `0x180036394`
- `0x180069038`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18001d22a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18001d2f1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18001d22a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18001d2f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d32a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d3a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d3f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d414`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d451`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d32a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d3a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d3f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d414`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d451`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18001d322`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18001d39d`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18001d3eb`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18001d40c`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18001d322`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18001d39d`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18001d3eb`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18001d40c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d1fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d2c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d319`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d394`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d3e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d403`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d1fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d2c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d319`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d394`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d3e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d403`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d273`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d273`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001d283`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001d283`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d28d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d28d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001d1ec`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001d1ec`

## pseudocode

```c
void __fastcall CFastSyncController::_PrepForSyncThreadUninitCallback(__int64 a1)
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

  _InterlockedIncrement((volatile signed __int32 *)(a1 + 8));
  CoUninitialize();
  if ( *(_DWORD *)(a1 + 28) )
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
LABEL_27:
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
      goto LABEL_27;
    }
  }
LABEL_12:
  v4 = *(_QWORD *)(a1 + 32);
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
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 8), 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(__int64, __int64))a1)(a1, 1);
}

```

## disassembly

```asm
0x18001d1d0  push    rdi
0x18001d1d2  sub     rsp, 30h
0x18001d1d6  mov     [rsp+38h+arg_8], rbx
0x18001d1db  mov     rdi, rcx
0x18001d1de  mov     [rsp+38h+arg_10], rbp
0x18001d1e3  mov     [rsp+38h+arg_18], rsi
0x18001d1e8  lock inc dword ptr [rcx+8]
0x18001d1ec  call    cs:__imp_CoUninitialize
0x18001d1f2  cmp     dword ptr [rdi+1Ch], 0
0x18001d1f6  jz      loc_18001D2C6
0x18001d1fc  call    cs:__imp_GetCurrentThread
0x18001d202  mov     rbp, rax
0x18001d205  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d20c  lea     rsi, WPP_GLOBAL_Control
0x18001d213  cmp     rcx, rsi
0x18001d216  jz      short loc_18001D222
0x18001d218  test    byte ptr [rcx+1Ch], 20h
0x18001d21c  jnz     loc_18001D394
0x18001d222  mov     edx, 20000h; nPriority
0x18001d227  mov     rcx, rbp; hThread
0x18001d22a  call    cs:__imp_SetThreadPriority
0x18001d230  test    eax, eax
0x18001d232  jz      loc_18001D3D8
0x18001d238  mov     rax, cs:WPP_GLOBAL_Control
0x18001d23f  cmp     rax, rsi
0x18001d242  jz      short loc_18001D25D
0x18001d244  test    byte ptr [rax+1Ch], 20h
0x18001d248  jnz     loc_18001D3E2
0x18001d24e  cmp     rax, rsi
0x18001d251  jz      short loc_18001D25D
0x18001d253  test    byte ptr [rax+1Ch], 20h
0x18001d257  jnz     loc_18001D451
0x18001d25d  mov     rbx, [rdi+20h]
0x18001d261  mov     esi, 0FFFFFFFFh
0x18001d266  test    rbx, rbx
0x18001d269  jz      short loc_18001D2A3
0x18001d26b  lock inc dword ptr [rbx+8]
0x18001d26f  lea     rcx, [rbx+20h]; lpCriticalSection
0x18001d273  call    cs:__imp_EnterCriticalSection
0x18001d279  sub     dword ptr [rbx+18h], 1
0x18001d27d  jnz     short loc_18001D289
0x18001d27f  mov     rcx, [rbx+10h]; hEvent
0x18001d283  call    cs:__imp_SetEvent
0x18001d289  lea     rcx, [rbx+20h]; lpCriticalSection
0x18001d28d  call    cs:__imp_LeaveCriticalSection
0x18001d293  mov     eax, esi
0x18001d295  lock xadd [rbx+8], eax
0x18001d29a  cmp     eax, 1
0x18001d29d  jz      loc_18001D37C
0x18001d2a3  lock xadd [rdi+8], esi
0x18001d2a8  mov     rbp, [rsp+38h+arg_10]
0x18001d2ad  cmp     esi, 1
0x18001d2b0  mov     rsi, [rsp+38h+arg_18]
0x18001d2b5  mov     rbx, [rsp+38h+arg_8]
0x18001d2ba  jz      loc_18001D364
0x18001d2c0  add     rsp, 30h
0x18001d2c4  pop     rdi
0x18001d2c5  retn
0x18001d2c6  call    cs:__imp_GetCurrentThread
0x18001d2cc  mov     rbp, rax
0x18001d2cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d2d6  lea     rsi, WPP_GLOBAL_Control
0x18001d2dd  cmp     rcx, rsi
0x18001d2e0  jz      short loc_18001D2EC
0x18001d2e2  test    byte ptr [rcx+1Ch], 20h
0x18001d2e6  jnz     loc_18001D403
0x18001d2ec  xor     edx, edx; nPriority
0x18001d2ee  mov     rcx, rbp; hThread
0x18001d2f1  call    cs:__imp_SetThreadPriority
0x18001d2f7  test    eax, eax
0x18001d2f9  jz      loc_18001D447
0x18001d2ff  mov     rax, cs:WPP_GLOBAL_Control
0x18001d306  cmp     rax, rsi
0x18001d309  jz      loc_18001D25D
0x18001d30f  test    byte ptr [rax+1Ch], 20h
0x18001d313  jz      loc_18001D24E
0x18001d319  call    cs:__imp_GetCurrentThread
0x18001d31f  mov     rcx, rax; hThread
0x18001d322  call    cs:__imp_GetThreadPriority
0x18001d328  mov     ebx, eax
0x18001d32a  call    cs:__imp_GetCurrentThreadId
0x18001d330  mov     byte ptr [rsp+38h+var_10], 4Eh ; 'N'
0x18001d335  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d33c  lea     r8, WPP_7967f24143133d59f1b33f7a742017bc_Traceguids
0x18001d343  mov     r9d, eax
0x18001d346  mov     [rsp+38h+var_18], ebx
0x18001d34a  mov     edx, 6Ch ; 'l'
0x18001d34f  mov     rcx, [rcx+10h]
0x18001d353  call    WPP_SF_DDc
0x18001d358  mov     rax, cs:WPP_GLOBAL_Control
0x18001d35f  jmp     loc_18001D24E
0x18001d364  mov     rax, [rdi]
0x18001d367  mov     edx, 1
0x18001d36c  mov     rcx, rdi
0x18001d36f  mov     rax, [rax]
0x18001d372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d377  jmp     loc_18001D2C0
0x18001d37c  mov     rax, [rbx]
0x18001d37f  mov     edx, 1
0x18001d384  mov     rcx, rbx
0x18001d387  mov     rax, [rax]
0x18001d38a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d38f  jmp     loc_18001D2A3
0x18001d394  call    cs:__imp_GetCurrentThread
0x18001d39a  mov     rcx, rax; hThread
0x18001d39d  call    cs:__imp_GetThreadPriority
0x18001d3a3  mov     ebx, eax
0x18001d3a5  call    cs:__imp_GetCurrentThreadId
0x18001d3ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d3b2  lea     r8, WPP_7967f24143133d59f1b33f7a742017bc_Traceguids
0x18001d3b9  mov     edx, 6Bh ; 'k'
0x18001d3be  mov     byte ptr [rsp+38h+var_10], 59h ; 'Y'
0x18001d3c3  mov     r9d, eax
0x18001d3c6  mov     [rsp+38h+var_18], ebx
0x18001d3ca  mov     rcx, [rcx+10h]
0x18001d3ce  call    WPP_SF_DDc
0x18001d3d3  jmp     loc_18001D222
0x18001d3d8  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18001d3dd  jmp     loc_18001D238
0x18001d3e2  call    cs:__imp_GetCurrentThread
0x18001d3e8  mov     rcx, rax; hThread
0x18001d3eb  call    cs:__imp_GetThreadPriority
0x18001d3f1  mov     ebx, eax
0x18001d3f3  call    cs:__imp_GetCurrentThreadId
0x18001d3f9  mov     byte ptr [rsp+38h+var_10], 59h ; 'Y'
0x18001d3fe  jmp     loc_18001D335
0x18001d403  call    cs:__imp_GetCurrentThread
0x18001d409  mov     rcx, rax; hThread
0x18001d40c  call    cs:__imp_GetThreadPriority
0x18001d412  mov     ebx, eax
0x18001d414  call    cs:__imp_GetCurrentThreadId
0x18001d41a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d421  lea     r8, WPP_7967f24143133d59f1b33f7a742017bc_Traceguids
0x18001d428  mov     edx, 6Bh ; 'k'
0x18001d42d  mov     byte ptr [rsp+38h+var_10], 4Eh ; 'N'
0x18001d432  mov     r9d, eax
0x18001d435  mov     [rsp+38h+var_18], ebx
0x18001d439  mov     rcx, [rcx+10h]
0x18001d43d  call    WPP_SF_DDc
0x18001d442  jmp     loc_18001D2EC
0x18001d447  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18001d44c  jmp     loc_18001D2FF
0x18001d451  call    cs:__imp_GetCurrentThreadId
0x18001d457  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d45e  lea     r8, WPP_7967f24143133d59f1b33f7a742017bc_Traceguids
0x18001d465  mov     edx, 71h ; 'q'
0x18001d46a  mov     r9d, eax
0x18001d46d  mov     rcx, [rcx+10h]
0x18001d471  call    WPP_SF_d
0x18001d476  jmp     loc_18001D25D
```
