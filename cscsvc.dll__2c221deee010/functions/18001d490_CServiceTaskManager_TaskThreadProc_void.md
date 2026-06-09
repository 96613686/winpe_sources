# CServiceTaskManager::_TaskThreadProc(void *)

- ea: `0x18001d490`
- end: `0x18001d8fa`
- name: `?_TaskThreadProc@CServiceTaskManager@@CAKPEAX@Z`
- size: `1130`
- prototype: `__int64 __fastcall(_DWORD *Parameter)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000d640`
- `0x18001b4e0`
- `0x18001d490`
- `0x18002cef4`
- `0x18002f10c`
- `0x1800361cc`
- `0x180036394`
- `0x18003c4e8`
- `0x180069454`
- `0x180069530`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d7a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d7a2`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18001d770`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18001d770`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18001d8f3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18001d8f3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18001d53a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18001d5e3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18001d53a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18001d5e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d4dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d4dd`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18001d4fe`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18001d4fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d4f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d52d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d5d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d4f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d52d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d5d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d4aa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d5b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d785`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d4aa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d5b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d785`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d584`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d67a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d751`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d584`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d67a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d751`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001d5a8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001d5a8`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001d83d`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001d83d`

## pseudocode

```c
__int64 __fastcall CServiceTaskManager::_TaskThreadProc(_DWORD *Parameter)
{
  CServiceTaskManager *v2; // rcx
  HMODULE LibraryW; // r12
  _DWORD *v4; // rsi
  DWORD CurrentThreadId; // eax
  bool v6; // zf
  HANDLE CurrentThread; // rax
  int ThreadPriority; // r14d
  int v9; // ebx
  HANDLE v10; // rax
  int Error; // ebp
  int v12; // ebp
  DWORD v13; // r15d
  int v14; // ebx
  HANDLE v15; // rax
  __int64 i; // rdx
  CObjectMonitor *v18; // r10
  __int64 v19; // rax
  __int64 v20; // r10
  __int64 v21; // r8
  const WCHAR *v22; // rcx
  unsigned int ConstBuffer; // eax
  char v24; // r8
  __int64 v25; // rax
  __int64 v26; // r10
  __int64 v27; // r8
  HRESULT v28; // eax
  __int64 v29; // rax
  __int64 v30; // r10
  __int64 v31; // r8
  void *v32; // rdx

  EnterCriticalSection(&stru_1800B7658);
  LibraryW = 0;
  if ( !Parameter[9] )
  {
    LeaveCriticalSection(&stru_1800B7658);
    v22 = (const WCHAR *)off_1800B7628[0];
    if ( lpLibFileName != (LPCWSTR)off_1800B7638 )
      v22 = lpLibFileName;
    LibraryW = LoadLibraryW(v22);
    if ( !LibraryW
      && WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      GetLastError();
      ConstBuffer = (unsigned int)CPath::_GetConstBuffer((CPath *)qword_1800B7418);
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        (unsigned int)WPP_088402f2fc59396373c04b0fd13246f5_Traceguids,
        ConstBuffer,
        v24);
    }
    EnterCriticalSection(&stru_1800B7658);
  }
  if ( !HIDWORD(qword_1800B7408) )
    goto LABEL_24;
  v4 = (_DWORD *)*((_QWORD *)Parameter + 7);
  CurrentThreadId = GetCurrentThreadId();
  v6 = Parameter[2] == 2;
  Parameter[7] = CurrentThreadId;
  if ( v6 )
  {
    CurrentThread = GetCurrentThread();
    ThreadPriority = GetThreadPriority(CurrentThread);
    if ( ThreadPriority != 0x7FFFFFFF || (int)ResultFromLastError() >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)v4 + 32LL))(v4);
      v10 = GetCurrentThread();
      Error = 0;
      if ( !SetThreadPriority(v10, v9) )
        Error = ResultFromLastError();
      if ( Error >= 0 )
      {
        v12 = Parameter[4];
        v13 = Parameter[5];
        if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
        {
          Tasks_TaskStateText(4);
          v25 = Tasks_TaskStateText((unsigned int)Parameter[2]);
          WPP_SF_SdSS(*(_QWORD *)(v26 + 16), 26, v27, (_DWORD)v4 + 20, v4[4], v25, v27);
        }
        Parameter[2] = 4;
        LeaveCriticalSection(&stru_1800B7658);
        v14 = 0;
        if ( v12 )
        {
          v28 = CoInitializeEx(0, v13);
          if ( v28 < 0 )
          {
            if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                27,
                WPP_088402f2fc59396373c04b0fd13246f5_Traceguids,
                (unsigned int)v28);
            }
            goto LABEL_14;
          }
          v14 = 1;
        }
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)Parameter + 7) + 8LL))(*((_QWORD *)Parameter + 7));
        if ( v14 )
          CoUninitialize();
LABEL_14:
        EnterCriticalSection(&stru_1800B7658);
        if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
        {
          Tasks_TaskStateText(5);
          v19 = Tasks_TaskStateText((unsigned int)Parameter[2]);
          WPP_SF_SdSS(*(_QWORD *)(v20 + 16), 28, v21, (_DWORD)v4 + 20, v4[4], v19, v21);
        }
        Parameter[2] = 5;
        v15 = GetCurrentThread();
        if ( !SetThreadPriority(v15, ThreadPriority) )
          ResultFromLastError();
      }
    }
  }
  if ( !Parameter[6] || Parameter[11] )
  {
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v4 + 24LL))(v4);
    for ( i = 0; (unsigned int)i < (unsigned int)qword_1800B7408; i = (unsigned int)(i + 1) )
    {
      v2 = *(CServiceTaskManager **)(g_TaskManager + 8 * i);
      if ( v2 && *((_DWORD *)v2 + 1) == Parameter[1] )
      {
        CServiceTaskManager::_RemoveTaskDescriptorAtIndex((CServiceTaskManager *)&g_TaskManager, i);
        break;
      }
    }
  }
  else
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
      {
        Tasks_TaskStateText(1);
        v29 = Tasks_TaskStateText((unsigned int)Parameter[2]);
        WPP_SF_SdSS(*(_QWORD *)(v30 + 16), 29, v31, (_DWORD)v4 + 20, v4[4], v29, v31);
        v18 = WPP_GLOBAL_Control;
      }
      if ( v18 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_DWORD *)v18 + 7) & 0x400000) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)v18 + 2),
          30,
          (unsigned int)WPP_088402f2fc59396373c04b0fd13246f5_Traceguids,
          (_DWORD)v4 + 20,
          Parameter[6]);
    }
    Parameter[2] = 1;
    Parameter[7] = 0;
  }
LABEL_24:
  if ( _InterlockedExchangeAdd(Parameter, 0xFFFFFFFF) == 1 )
  {
    CServiceTaskManager::_DestroyTaskDescriptor(v2, (struct TASK_DESCRIPTOR *)Parameter);
    CscUtil_HeapFree(Parameter, v32);
  }
  LeaveCriticalSection(&stru_1800B7658);
  if ( LibraryW )
    FreeLibraryAndExitThread(LibraryW, 0);
  return 0;
}

```

## disassembly

```asm
0x18001d490  push    r12
0x18001d492  sub     rsp, 60h
0x18001d496  mov     [rsp+68h+var_10], rdi
0x18001d49b  mov     rdi, rcx
0x18001d49e  lea     rcx, stru_1800B7658; lpCriticalSection
0x18001d4a5  mov     [rsp+68h+var_18], r13
0x18001d4aa  call    cs:__imp_EnterCriticalSection
0x18001d4b0  xor     r12d, r12d
0x18001d4b3  lea     r13, WPP_GLOBAL_Control
0x18001d4ba  cmp     [rdi+24h], r12d
0x18001d4be  jz      loc_18001D74A
0x18001d4c4  cmp     dword ptr cs:qword_1800B7408+4, 0
0x18001d4cb  jz      loc_18001D65C
0x18001d4d1  mov     [rsp+68h+arg_10], rsi
0x18001d4d9  mov     rsi, [rdi+38h]
0x18001d4dd  call    cs:__imp_GetCurrentThreadId
0x18001d4e3  cmp     dword ptr [rdi+8], 2
0x18001d4e7  mov     [rdi+1Ch], eax
0x18001d4ea  jnz     loc_18001D600
0x18001d4f0  mov     [rsp+68h+var_20], r14
0x18001d4f5  call    cs:__imp_GetCurrentThread
0x18001d4fb  mov     rcx, rax; hThread
0x18001d4fe  call    cs:__imp_GetThreadPriority
0x18001d504  mov     r14d, eax
0x18001d507  cmp     eax, 7FFFFFFFh
0x18001d50c  jz      loc_18001D7DD
0x18001d512  mov     rcx, [rsi]
0x18001d515  mov     [rsp+68h+arg_0], rbx
0x18001d51a  mov     [rsp+68h+arg_8], rbp
0x18001d51f  mov     rax, [rcx+20h]
0x18001d523  mov     rcx, rsi
0x18001d526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d52b  mov     ebx, eax
0x18001d52d  call    cs:__imp_GetCurrentThread
0x18001d533  mov     edx, ebx; nPriority
0x18001d535  xor     ebp, ebp
0x18001d537  mov     rcx, rax; hThread
0x18001d53a  call    cs:__imp_SetThreadPriority
0x18001d540  test    eax, eax
0x18001d542  jz      loc_18001D7EF
0x18001d548  test    ebp, ebp
0x18001d54a  js      loc_18001D5F1
0x18001d550  mov     ebp, [rdi+10h]
0x18001d553  mov     [rsp+68h+var_28], r15
0x18001d558  mov     r15d, [rdi+14h]
0x18001d55c  mov     r10, cs:WPP_GLOBAL_Control
0x18001d563  cmp     r10, r13
0x18001d566  jz      short loc_18001D576
0x18001d568  test    dword ptr [r10+1Ch], 400000h
0x18001d570  jnz     loc_18001D7FB
0x18001d576  lea     rcx, stru_1800B7658; lpCriticalSection
0x18001d57d  mov     dword ptr [rdi+8], 4
0x18001d584  call    cs:__imp_LeaveCriticalSection
0x18001d58a  xor     ebx, ebx
0x18001d58c  test    ebp, ebp
0x18001d58e  jnz     loc_18001D838
0x18001d594  mov     rcx, [rdi+38h]
0x18001d598  mov     rax, [rcx]
0x18001d59b  mov     rax, [rax+8]
0x18001d59f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5a4  test    ebx, ebx
0x18001d5a6  jz      short loc_18001D5AE
0x18001d5a8  call    cs:__imp_CoUninitialize
0x18001d5ae  lea     rcx, stru_1800B7658; lpCriticalSection
0x18001d5b5  call    cs:__imp_EnterCriticalSection
0x18001d5bb  mov     r10, cs:WPP_GLOBAL_Control
0x18001d5c2  mov     r15, [rsp+68h+var_28]
0x18001d5c7  cmp     r10, r13
0x18001d5ca  jnz     loc_18001D6BD
0x18001d5d0  mov     dword ptr [rdi+8], 5
0x18001d5d7  call    cs:__imp_GetCurrentThread
0x18001d5dd  mov     rcx, rax; hThread
0x18001d5e0  mov     edx, r14d; nPriority
0x18001d5e3  call    cs:__imp_SetThreadPriority
0x18001d5e9  test    eax, eax
0x18001d5eb  jz      loc_18001D88B
0x18001d5f1  mov     rbx, [rsp+68h+arg_0]
0x18001d5f6  mov     rbp, [rsp+68h+arg_8]
0x18001d5fb  mov     r14, [rsp+68h+var_20]
0x18001d600  cmp     dword ptr [rdi+18h], 0
0x18001d604  jnz     loc_18001D697
0x18001d60a  mov     rax, [rsi]
0x18001d60d  mov     rcx, rsi
0x18001d610  mov     rax, [rax+18h]
0x18001d614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d619  mov     r10d, [rdi+4]
0x18001d61d  xor     edx, edx; unsigned int
0x18001d61f  mov     r8, cs:qword_1800B7408
0x18001d626  mov     r9, cs:?g_TaskManager@@3VCServiceTaskManager@@A; CServiceTaskManager g_TaskManager
0x18001d62d  nop     dword ptr [rax]
0x18001d630  cmp     edx, r8d
0x18001d633  jnb     short loc_18001D654
0x18001d635  mov     rcx, [r9+rdx*8]
0x18001d639  test    rcx, rcx
0x18001d63c  jnz     short loc_18001D642
0x18001d63e  inc     edx
0x18001d640  jmp     short loc_18001D630
0x18001d642  cmp     [rcx+4], r10d
0x18001d646  jnz     short loc_18001D63E
0x18001d648  lea     rcx, ?g_TaskManager@@3VCServiceTaskManager@@A; this
0x18001d64f  call    ?_RemoveTaskDescriptorAtIndex@CServiceTaskManager@@AEAAXK@Z; CServiceTaskManager::_RemoveTaskDescriptorAtIndex(ulong)
0x18001d654  mov     rsi, [rsp+68h+arg_10]
0x18001d65c  mov     eax, 0FFFFFFFFh
0x18001d661  lock xadd [rdi], eax
0x18001d665  mov     r13, [rsp+68h+var_18]
0x18001d66a  cmp     eax, 1
0x18001d66d  jz      loc_18001D8D9
0x18001d673  lea     rcx, stru_1800B7658; lpCriticalSection
0x18001d67a  call    cs:__imp_LeaveCriticalSection
0x18001d680  mov     rdi, [rsp+68h+var_10]
0x18001d685  test    r12, r12
0x18001d688  jnz     loc_18001D8EE
0x18001d68e  xor     eax, eax
0x18001d690  add     rsp, 60h
0x18001d694  pop     r12
0x18001d696  retn
0x18001d697  cmp     dword ptr [rdi+2Ch], 0
0x18001d69b  jnz     loc_18001D60A
0x18001d6a1  mov     r10, cs:WPP_GLOBAL_Control
0x18001d6a8  cmp     r10, r13
0x18001d6ab  jnz     short loc_18001D708
0x18001d6ad  mov     dword ptr [rdi+8], 1
0x18001d6b4  mov     dword ptr [rdi+1Ch], 0
0x18001d6bb  jmp     short loc_18001D654
0x18001d6bd  test    dword ptr [r10+1Ch], 400000h
0x18001d6c5  jz      loc_18001D5D0
0x18001d6cb  mov     ecx, 5
0x18001d6d0  call    Tasks_TaskStateText
0x18001d6d5  mov     ecx, [rdi+8]
0x18001d6d8  mov     r8, rax
0x18001d6db  call    Tasks_TaskStateText
0x18001d6e0  mov     rcx, [r10+10h]
0x18001d6e4  lea     r9, [rsi+14h]
0x18001d6e8  mov     [rsp+68h+var_38], r8
0x18001d6ed  mov     edx, 1Ch
0x18001d6f2  mov     [rsp+68h+var_40], rax
0x18001d6f7  mov     eax, [rsi+10h]
0x18001d6fa  mov     [rsp+68h+var_48], eax
0x18001d6fe  call    WPP_SF_SdSS
0x18001d703  jmp     loc_18001D5D0
0x18001d708  test    dword ptr [r10+1Ch], 400000h
0x18001d710  jnz     loc_18001D895
0x18001d716  cmp     r10, r13
0x18001d719  jz      short loc_18001D6AD
0x18001d71b  test    dword ptr [r10+1Ch], 400000h
0x18001d723  jz      short loc_18001D6AD
0x18001d725  mov     eax, [rdi+18h]
0x18001d728  lea     r9, [rsi+14h]
0x18001d72c  mov     rcx, [r10+10h]
0x18001d730  lea     r8, WPP_088402f2fc59396373c04b0fd13246f5_Traceguids
0x18001d737  mov     edx, 1Eh
0x18001d73c  mov     [rsp+68h+var_48], eax
0x18001d740  call    WPP_SF_Sd
0x18001d745  jmp     loc_18001D6AD
0x18001d74a  lea     rcx, stru_1800B7658; lpCriticalSection
0x18001d751  call    cs:__imp_LeaveCriticalSection
0x18001d757  mov     rax, cs:lpLibFileName
0x18001d75e  cmp     rax, cs:off_1800B7638
0x18001d765  mov     rcx, cs:off_1800B7628
0x18001d76c  cmovnz  rcx, rax; lpLibFileName
0x18001d770  call    cs:__imp_LoadLibraryW
0x18001d776  mov     r12, rax
0x18001d779  test    rax, rax
0x18001d77c  jz      short loc_18001D790
0x18001d77e  lea     rcx, stru_1800B7658; lpCriticalSection
0x18001d785  call    cs:__imp_EnterCriticalSection
0x18001d78b  jmp     loc_18001D4C4
0x18001d790  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d797  cmp     rcx, r13
0x18001d79a  jz      short loc_18001D77E
0x18001d79c  test    byte ptr [rcx+1Ch], 2
0x18001d7a0  jz      short loc_18001D77E
0x18001d7a2  call    cs:__imp_GetLastError
0x18001d7a8  lea     rcx, qword_1800B7418; this
0x18001d7af  mov     r8d, eax
0x18001d7b2  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x18001d7b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d7be  mov     r9, rax
0x18001d7c1  mov     [rsp+68h+var_48], r8d
0x18001d7c6  mov     edx, 19h
0x18001d7cb  lea     r8, WPP_088402f2fc59396373c04b0fd13246f5_Traceguids
0x18001d7d2  mov     rcx, [rcx+10h]
0x18001d7d6  call    WPP_SF_Sd
0x18001d7db  jmp     short loc_18001D77E
0x18001d7dd  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18001d7e2  test    eax, eax
0x18001d7e4  js      loc_18001D5FB
0x18001d7ea  jmp     loc_18001D512
0x18001d7ef  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18001d7f4  mov     ebp, eax
0x18001d7f6  jmp     loc_18001D548
0x18001d7fb  mov     ecx, 4
0x18001d800  call    Tasks_TaskStateText
0x18001d805  mov     ecx, [rdi+8]
0x18001d808  mov     r8, rax
0x18001d80b  call    Tasks_TaskStateText
0x18001d810  mov     rcx, [r10+10h]
0x18001d814  lea     r9, [rsi+14h]
0x18001d818  mov     [rsp+68h+var_38], r8
0x18001d81d  mov     edx, 1Ah
0x18001d822  mov     [rsp+68h+var_40], rax
0x18001d827  mov     eax, [rsi+10h]
0x18001d82a  mov     [rsp+68h+var_48], eax
0x18001d82e  call    WPP_SF_SdSS
0x18001d833  jmp     loc_18001D576
0x18001d838  mov     edx, r15d; dwCoInit
0x18001d83b  xor     ecx, ecx; pvReserved
0x18001d83d  call    cs:__imp_CoInitializeEx
0x18001d843  test    eax, eax
0x18001d845  js      short loc_18001D851
0x18001d847  mov     ebx, 1
0x18001d84c  jmp     loc_18001D594
0x18001d851  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d858  cmp     rcx, r13
0x18001d85b  jz      loc_18001D5AE
0x18001d861  test    dword ptr [rcx+1Ch], 400000h
0x18001d868  jz      loc_18001D5AE
0x18001d86e  mov     rcx, [rcx+10h]
0x18001d872  lea     r8, WPP_088402f2fc59396373c04b0fd13246f5_Traceguids
0x18001d879  mov     edx, 1Bh
0x18001d87e  mov     r9d, eax
0x18001d881  call    WPP_SF_d
0x18001d886  jmp     loc_18001D5AE
0x18001d88b  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18001d890  jmp     loc_18001D5F1
0x18001d895  mov     ecx, 1
0x18001d89a  call    Tasks_TaskStateText
0x18001d89f  mov     ecx, [rdi+8]
0x18001d8a2  mov     r8, rax
0x18001d8a5  call    Tasks_TaskStateText
0x18001d8aa  mov     rcx, [r10+10h]
0x18001d8ae  lea     r9, [rsi+14h]
0x18001d8b2  mov     [rsp+68h+var_38], r8
0x18001d8b7  mov     edx, 1Dh
0x18001d8bc  mov     [rsp+68h+var_40], rax
0x18001d8c1  mov     eax, [rsi+10h]
0x18001d8c4  mov     [rsp+68h+var_48], eax
0x18001d8c8  call    WPP_SF_SdSS
0x18001d8cd  mov     r10, cs:WPP_GLOBAL_Control
0x18001d8d4  jmp     loc_18001D716
0x18001d8d9  mov     rdx, rdi; struct TASK_DESCRIPTOR *
0x18001d8dc  call    ?_DestroyTaskDescriptor@CServiceTaskManager@@AEAAXPEAUTASK_DESCRIPTOR@@@Z; CServiceTaskManager::_DestroyTaskDescriptor(TASK_DESCRIPTOR *)
0x18001d8e1  mov     rcx, rdi; lpMem
0x18001d8e4  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x18001d8e9  jmp     loc_18001D673
0x18001d8ee  xor     edx, edx; dwExitCode
0x18001d8f0  mov     rcx, r12; hLibModule
0x18001d8f3  call    cs:__imp_FreeLibraryAndExitThread
```
