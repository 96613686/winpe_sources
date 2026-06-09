# CFastSyncController::_InitFastSyncThread(void)

- ea: `0x1800189a0`
- end: `0x180018c7e`
- name: `?_InitFastSyncThread@CFastSyncController@@AEAAHXZ`
- size: `734`
- prototype: `_BOOL8 __fastcall(CFastSyncController *this)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180018940`
- `0x1800302e0`

## callees

- `0x1800189a0`
- `0x180018c90`
- `0x18002f10c`
- `0x180036394`
- `0x18003c460`
- `0x180069038`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018aac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018aac`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800189e8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800189e8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018b1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018b6d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018bdb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018b1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018b6d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018bdb`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x180018b15`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x180018b65`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x180018b15`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x180018b65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800189bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180018aeb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180018b0c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180018b5c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180018c32`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800189bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180018aeb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180018b0c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180018b5c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180018c32`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018a70`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018a70`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180018a87`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180018a87`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018a91`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018a91`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180018bc9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180018bc9`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180018a2a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180018a2a`

## pseudocode

```c
_BOOL8 __fastcall CFastSyncController::_InitFastSyncThread(CFastSyncController *this)
{
  HANDLE v2; // rbp
  int Error; // ebx
  CObjectMonitor *v4; // rcx
  int v5; // edi
  HRESULT v6; // eax
  __int64 v7; // rax
  __int64 v8; // rdi
  int v9; // edx
  __int64 v10; // rcx
  DWORD v11; // ecx
  int v13; // ebx
  HANDLE CurrentThread; // rax
  HANDLE v15; // rax
  int ThreadPriority; // edi
  DWORD CurrentThreadId; // eax
  HANDLE v18; // rax
  int v19; // edi
  DWORD v20; // eax
  DWORD v21; // eax
  int v22; // edi
  HANDLE v23; // rax
  int v24; // edx
  int v25; // [rsp+28h] [rbp-30h]

  if ( !*((_DWORD *)this + 7) )
  {
    v13 = *((_DWORD *)this + 6);
    CurrentThread = GetCurrentThread();
    Error = CscUtil_SetThreadPriorityTrace(CurrentThread, v13, 0);
LABEL_28:
    v4 = WPP_GLOBAL_Control;
    goto LABEL_9;
  }
  v2 = GetCurrentThread();
  Error = 0;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    v15 = GetCurrentThread();
    ThreadPriority = GetThreadPriority(v15);
    CurrentThreadId = GetCurrentThreadId();
    WPP_SF_DDc(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      107,
      WPP_7967f24143133d59f1b33f7a742017bc_Traceguids,
      CurrentThreadId,
      ThreadPriority,
      89);
  }
  if ( !SetThreadPriority(v2, 0x10000) )
    Error = ResultFromLastError();
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    v18 = GetCurrentThread();
    v19 = GetThreadPriority(v18);
    v20 = GetCurrentThreadId();
    LOBYTE(v25) = 89;
    WPP_SF_DDc(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, WPP_7967f24143133d59f1b33f7a742017bc_Traceguids, v20, v19, v25);
    goto LABEL_28;
  }
LABEL_9:
  if ( Error < 0 )
  {
    if ( v4 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)v4 + 2), 111, WPP_7967f24143133d59f1b33f7a742017bc_Traceguids, (unsigned int)Error);
  }
  else
  {
    v5 = 10;
    Error = -2147417850;
    while ( v5 )
    {
      v6 = CoInitializeEx(0, 0);
      Error = v6;
      if ( v6 != -2147417850 )
      {
        if ( v6 >= 0 )
        {
          if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
          {
            v21 = GetCurrentThreadId();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, WPP_7967f24143133d59f1b33f7a742017bc_Traceguids, v21);
          }
          v7 = *((_QWORD *)this + 4);
          if ( v7 )
          {
            _InterlockedIncrement((volatile signed __int32 *)(v7 + 8));
            v8 = *((_QWORD *)this + 4);
            EnterCriticalSection((LPCRITICAL_SECTION)(v8 + 32));
            v9 = *(_DWORD *)(v8 + 24);
            *(_DWORD *)(v8 + 24) = v9 + 1;
            if ( !v9 )
              ResetEvent(*(HANDLE *)(v8 + 16));
            LeaveCriticalSection((LPCRITICAL_SECTION)(v8 + 32));
            v10 = *((_QWORD *)this + 4);
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v10 + 8), 0xFFFFFFFF) == 1 && v10 )
              (**(void (__fastcall ***)(__int64, __int64))v10)(v10, 1);
          }
          v11 = 0;
          goto LABEL_22;
        }
        v4 = WPP_GLOBAL_Control;
        break;
      }
      --v5;
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, WPP_7967f24143133d59f1b33f7a742017bc_Traceguids);
      }
      CoUninitialize();
      v4 = WPP_GLOBAL_Control;
    }
    if ( v4 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)v4 + 2), 110, WPP_7967f24143133d59f1b33f7a742017bc_Traceguids, (unsigned int)Error);
    v22 = *((_DWORD *)this + 7);
    v23 = GetCurrentThread();
    if ( v22 )
    {
      v24 = 0x20000;
    }
    else
    {
      v24 = 0;
      v22 = 0;
    }
    CscUtil_SetThreadPriorityTrace(v23, v24, v22);
  }
  v11 = Error;
LABEL_22:
  SetLastError(v11);
  return Error >= 0;
}

```

## disassembly

```asm
0x1800189a0  push    rbx
0x1800189a2  push    rbp
0x1800189a3  push    rsi
0x1800189a4  push    rdi
0x1800189a5  push    r14
0x1800189a7  sub     rsp, 30h
0x1800189ab  cmp     dword ptr [rcx+1Ch], 0
0x1800189af  lea     r14, WPP_GLOBAL_Control
0x1800189b6  mov     rsi, rcx
0x1800189b9  jz      loc_180018AE8
0x1800189bf  call    cs:__imp_GetCurrentThread
0x1800189c5  mov     rbp, rax
0x1800189c8  xor     ebx, ebx
0x1800189ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800189d1  cmp     rcx, r14
0x1800189d4  jz      short loc_1800189E0
0x1800189d6  test    byte ptr [rcx+1Ch], 20h
0x1800189da  jnz     loc_180018B0C
0x1800189e0  mov     edx, 10000h; nPriority
0x1800189e5  mov     rcx, rbp; hThread
0x1800189e8  call    cs:__imp_SetThreadPriority
0x1800189ee  test    eax, eax
0x1800189f0  jz      loc_180018B50
0x1800189f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800189fd  cmp     rcx, r14
0x180018a00  jz      short loc_180018A0C
0x180018a02  test    byte ptr [rcx+1Ch], 20h
0x180018a06  jnz     loc_180018B5C
0x180018a0c  test    ebx, ebx
0x180018a0e  js      loc_180018AC4
0x180018a14  mov     edi, 0Ah
0x180018a19  mov     ebx, 80010106h
0x180018a1e  test    edi, edi
0x180018a20  jz      loc_180018C0C
0x180018a26  xor     edx, edx; dwCoInit
0x180018a28  xor     ecx, ecx; pvReserved
0x180018a2a  call    cs:__imp_CoInitializeEx
0x180018a30  mov     ebx, eax
0x180018a32  cmp     eax, 80010106h
0x180018a37  jz      loc_180018BA0
0x180018a3d  test    eax, eax
0x180018a3f  js      loc_180018C05
0x180018a45  mov     rax, cs:WPP_GLOBAL_Control
0x180018a4c  cmp     rax, r14
0x180018a4f  jz      short loc_180018A5B
0x180018a51  test    byte ptr [rax+1Ch], 20h
0x180018a55  jnz     loc_180018BDB
0x180018a5b  mov     rax, [rsi+20h]
0x180018a5f  test    rax, rax
0x180018a62  jz      short loc_180018AAA
0x180018a64  lock inc dword ptr [rax+8]
0x180018a68  mov     rdi, [rsi+20h]
0x180018a6c  lea     rcx, [rdi+20h]; lpCriticalSection
0x180018a70  call    cs:__imp_EnterCriticalSection
0x180018a76  mov     edx, [rdi+18h]
0x180018a79  lea     eax, [rdx+1]
0x180018a7c  mov     [rdi+18h], eax
0x180018a7f  test    edx, edx
0x180018a81  jnz     short loc_180018A8D
0x180018a83  mov     rcx, [rdi+10h]; hEvent
0x180018a87  call    cs:__imp_ResetEvent
0x180018a8d  lea     rcx, [rdi+20h]; lpCriticalSection
0x180018a91  call    cs:__imp_LeaveCriticalSection
0x180018a97  mov     rcx, [rsi+20h]
0x180018a9b  mov     eax, 0FFFFFFFFh
0x180018aa0  lock xadd [rcx+8], eax
0x180018aa5  cmp     eax, 1
0x180018aa8  jz      short loc_180018AD1
0x180018aaa  xor     ecx, ecx; dwErrCode
0x180018aac  call    cs:__imp_SetLastError
0x180018ab2  not     ebx
0x180018ab4  shr     ebx, 1Fh
0x180018ab7  mov     eax, ebx
0x180018ab9  add     rsp, 30h
0x180018abd  pop     r14
0x180018abf  pop     rdi
0x180018ac0  pop     rsi
0x180018ac1  pop     rbp
0x180018ac2  pop     rbx
0x180018ac3  retn
0x180018ac4  cmp     rcx, r14
0x180018ac7  jnz     loc_180018C57
0x180018acd  mov     ecx, ebx
0x180018acf  jmp     short loc_180018AAC
0x180018ad1  test    rcx, rcx
0x180018ad4  jz      short loc_180018AAA
0x180018ad6  mov     rax, [rcx]
0x180018ad9  mov     edx, 1
0x180018ade  mov     rax, [rax]
0x180018ae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ae6  jmp     short loc_180018AAA
0x180018ae8  mov     ebx, [rcx+18h]
0x180018aeb  call    cs:__imp_GetCurrentThread
0x180018af1  xor     r8d, r8d; int
0x180018af4  mov     edx, ebx; nPriority
0x180018af6  mov     rcx, rax; hThread
0x180018af9  call    ?CscUtil_SetThreadPriorityTrace@@YAJPEAXHH@Z; CscUtil_SetThreadPriorityTrace(void *,int,int)
0x180018afe  mov     ebx, eax
0x180018b00  mov     rcx, cs:WPP_GLOBAL_Control
0x180018b07  jmp     loc_180018A0C
0x180018b0c  call    cs:__imp_GetCurrentThread
0x180018b12  mov     rcx, rax; hThread
0x180018b15  call    cs:__imp_GetThreadPriority
0x180018b1b  mov     edi, eax
0x180018b1d  call    cs:__imp_GetCurrentThreadId
0x180018b23  mov     rcx, cs:WPP_GLOBAL_Control
0x180018b2a  lea     r8, WPP_7967f24143133d59f1b33f7a742017bc_Traceguids
0x180018b31  mov     edx, 6Bh ; 'k'
0x180018b36  mov     byte ptr [rsp+58h+var_30], 59h ; 'Y'
0x180018b3b  mov     r9d, eax
0x180018b3e  mov     [rsp+58h+var_38], edi
0x180018b42  mov     rcx, [rcx+10h]
0x180018b46  call    WPP_SF_DDc
0x180018b4b  jmp     loc_1800189E0
0x180018b50  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180018b55  mov     ebx, eax
0x180018b57  jmp     loc_1800189F6
0x180018b5c  call    cs:__imp_GetCurrentThread
0x180018b62  mov     rcx, rax; hThread
0x180018b65  call    cs:__imp_GetThreadPriority
0x180018b6b  mov     edi, eax
0x180018b6d  call    cs:__imp_GetCurrentThreadId
0x180018b73  mov     rcx, cs:WPP_GLOBAL_Control
0x180018b7a  lea     r8, WPP_7967f24143133d59f1b33f7a742017bc_Traceguids
0x180018b81  mov     edx, 6Ch ; 'l'
0x180018b86  mov     byte ptr [rsp+58h+var_30], 59h ; 'Y'
0x180018b8b  mov     r9d, eax
0x180018b8e  mov     [rsp+58h+var_38], edi
0x180018b92  mov     rcx, [rcx+10h]
0x180018b96  call    WPP_SF_DDc
0x180018b9b  jmp     loc_180018B00
0x180018ba0  dec     edi
0x180018ba2  mov     rcx, cs:WPP_GLOBAL_Control
0x180018ba9  cmp     rcx, r14
0x180018bac  jz      short loc_180018BC9
0x180018bae  test    byte ptr [rcx+1Ch], 20h
0x180018bb2  jz      short loc_180018BC9
0x180018bb4  mov     rcx, [rcx+10h]
0x180018bb8  lea     r8, WPP_7967f24143133d59f1b33f7a742017bc_Traceguids
0x180018bbf  mov     edx, 6Dh ; 'm'
0x180018bc4  call    WPP_SF_
0x180018bc9  call    cs:__imp_CoUninitialize
0x180018bcf  mov     rcx, cs:WPP_GLOBAL_Control
0x180018bd6  jmp     loc_180018A1E
0x180018bdb  call    cs:__imp_GetCurrentThreadId
0x180018be1  mov     rcx, cs:WPP_GLOBAL_Control
0x180018be8  lea     r8, WPP_7967f24143133d59f1b33f7a742017bc_Traceguids
0x180018bef  mov     edx, 70h ; 'p'
0x180018bf4  mov     r9d, eax
0x180018bf7  mov     rcx, [rcx+10h]
0x180018bfb  call    WPP_SF_d
0x180018c00  jmp     loc_180018A5B
0x180018c05  mov     rcx, cs:WPP_GLOBAL_Control
0x180018c0c  cmp     rcx, r14
0x180018c0f  jz      short loc_180018C2F
0x180018c11  test    byte ptr [rcx+1Ch], 2
0x180018c15  jz      short loc_180018C2F
0x180018c17  mov     rcx, [rcx+10h]
0x180018c1b  lea     r8, WPP_7967f24143133d59f1b33f7a742017bc_Traceguids
0x180018c22  mov     edx, 6Eh ; 'n'
0x180018c27  mov     r9d, ebx
0x180018c2a  call    WPP_SF_d
0x180018c2f  mov     edi, [rsi+1Ch]
0x180018c32  call    cs:__imp_GetCurrentThread
0x180018c38  test    edi, edi
0x180018c3a  jz      short loc_180018C43
0x180018c3c  mov     edx, 20000h
0x180018c41  jmp     short loc_180018C47
0x180018c43  xor     edx, edx; nPriority
0x180018c45  xor     edi, edi
0x180018c47  mov     r8d, edi; int
0x180018c4a  mov     rcx, rax; hThread
0x180018c4d  call    ?CscUtil_SetThreadPriorityTrace@@YAJPEAXHH@Z; CscUtil_SetThreadPriorityTrace(void *,int,int)
0x180018c52  jmp     loc_180018ACD
0x180018c57  test    byte ptr [rcx+1Ch], 2
0x180018c5b  jz      loc_180018ACD
0x180018c61  mov     rcx, [rcx+10h]
0x180018c65  lea     r8, WPP_7967f24143133d59f1b33f7a742017bc_Traceguids
0x180018c6c  mov     edx, 6Fh ; 'o'
0x180018c71  mov     r9d, ebx
0x180018c74  call    WPP_SF_d
0x180018c79  jmp     loc_180018ACD
```
