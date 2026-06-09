# RunService(void *)

- ea: `0x1800058d0`
- end: `0x180005a01`
- name: `?RunService@@YAIPEAX@Z`
- size: `305`
- prototype: `unsigned int __stdcall(void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callees

- `0x1800058d0`
- `0x180005a10`
- `0x18000997c`
- `0x18000b32c`
- `0x18000b598`
- `0x18002f5f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180005965`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800059c8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180005965`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800059c8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800059b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800059b1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000598f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000598f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000594e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000594e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800059d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800059d8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x1800059e8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x1800059e8`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800058ef`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800058ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180005912`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180005922`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180005912`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180005922`

## string_xrefs

- `0x1800058df`: `catsrv.dll`

## pseudocode

```c
__int64 __fastcall RunService(void *a1)
{
  HMODULE LibraryW; // rsi
  HANDLE CurrentProcess; // rax
  HANDLE v3; // rdi
  void *v4; // rbx
  HANDLE v5; // rax
  int v6; // ecx
  HANDLE v7; // rdx
  HANDLE TargetHandle; // [rsp+60h] [rbp+18h] BYREF

  TargetHandle = 0;
  LibraryW = LoadLibraryW(L"catsrv.dll");
  if ( (int)CoRegInitialize() >= 0 && (int)RegSrvrInit() >= 0 )
  {
    CurrentProcess = GetCurrentProcess();
    v3 = g_ThreadStopEvent;
    v4 = CurrentProcess;
    v5 = GetCurrentProcess();
    DuplicateHandle(v5, v3, v4, &TargetHandle, 0, 0, 2u);
    g_bThreadRunning = 1;
    SetEvent(g_ThreadStartEvent);
    v7 = g_ThreadStopEvent;
    if ( TargetHandle )
      v7 = TargetHandle;
    RegSrvrPump(v6, v7);
    RegSrvrUninit();
    EnterCriticalSection(&CriticalSection);
    if ( !--dword_180072FE8 )
      _RegReleaseReference((struct REGAPI_STATE *)&qword_180072DA0);
    LeaveCriticalSection(&CriticalSection);
    g_bThreadRunning = 0;
  }
  SetEvent(g_ThreadStartEvent);
  if ( TargetHandle )
    CloseHandle(TargetHandle);
  if ( LibraryW )
    FreeLibraryAndExitThread(LibraryW, 0);
  return 0;
}

```

## disassembly

```asm
0x1800058d0  mov     [rsp+arg_0], rbx
0x1800058d5  mov     [rsp+arg_18], rsi
0x1800058da  push    rdi
0x1800058db  sub     rsp, 40h
0x1800058df  lea     rcx, aCatsrvDll_0; "catsrv.dll"
0x1800058e6  mov     [rsp+48h+TargetHandle], 0
0x1800058ef  call    cs:__imp_LoadLibraryW
0x1800058f5  mov     rsi, rax
0x1800058f8  call    CoRegInitialize
0x1800058fd  test    eax, eax
0x1800058ff  js      loc_1800059C1
0x180005905  call    ?RegSrvrInit@@YAJXZ; RegSrvrInit(void)
0x18000590a  test    eax, eax
0x18000590c  js      loc_1800059C1
0x180005912  call    cs:__imp_GetCurrentProcess
0x180005918  mov     rdi, cs:?g_ThreadStopEvent@@3PEAXEA; void * g_ThreadStopEvent
0x18000591f  mov     rbx, rax
0x180005922  call    cs:__imp_GetCurrentProcess
0x180005928  mov     [rsp+48h+dwOptions], 2; dwOptions
0x180005930  lea     r9, [rsp+48h+TargetHandle]; lpTargetHandle
0x180005935  mov     rcx, rax; hSourceProcessHandle
0x180005938  mov     [rsp+48h+bInheritHandle], 0; bInheritHandle
0x180005940  mov     r8, rbx; hTargetProcessHandle
0x180005943  mov     [rsp+48h+dwDesiredAccess], 0; dwDesiredAccess
0x18000594b  mov     rdx, rdi; hSourceHandle
0x18000594e  call    cs:__imp_DuplicateHandle
0x180005954  mov     rcx, cs:?g_ThreadStartEvent@@3PEAXEA; hEvent
0x18000595b  mov     cs:?g_bThreadRunning@@3HA, 1; int g_bThreadRunning
0x180005965  call    cs:__imp_SetEvent
0x18000596b  mov     rax, [rsp+48h+TargetHandle]
0x180005970  mov     rdx, cs:?g_ThreadStopEvent@@3PEAXEA; void * g_ThreadStopEvent
0x180005977  test    rax, rax
0x18000597a  cmovnz  rdx, rax; void *
0x18000597e  call    ?RegSrvrPump@@YAJHPEAX@Z; RegSrvrPump(int,void *)
0x180005983  call    ?RegSrvrUninit@@YAXXZ; RegSrvrUninit(void)
0x180005988  lea     rcx, CriticalSection; lpCriticalSection
0x18000598f  call    cs:__imp_EnterCriticalSection
0x180005995  sub     cs:dword_180072FE8, 1
0x18000599c  jnz     short loc_1800059AA
0x18000599e  lea     rcx, qword_180072DA0; struct REGAPI_STATE *
0x1800059a5  call    ?_RegReleaseReference@@YAXPEAUREGAPI_STATE@@@Z; _RegReleaseReference(REGAPI_STATE *)
0x1800059aa  lea     rcx, CriticalSection; lpCriticalSection
0x1800059b1  call    cs:__imp_LeaveCriticalSection
0x1800059b7  mov     cs:?g_bThreadRunning@@3HA, 0; int g_bThreadRunning
0x1800059c1  mov     rcx, cs:?g_ThreadStartEvent@@3PEAXEA; hEvent
0x1800059c8  call    cs:__imp_SetEvent
0x1800059ce  mov     rcx, [rsp+48h+TargetHandle]; hObject
0x1800059d3  test    rcx, rcx
0x1800059d6  jz      short loc_1800059DE
0x1800059d8  call    cs:__imp_CloseHandle
0x1800059de  test    rsi, rsi
0x1800059e1  jz      short loc_1800059EF
0x1800059e3  xor     edx, edx; dwExitCode
0x1800059e5  mov     rcx, rsi; hLibModule
0x1800059e8  call    cs:__imp_FreeLibraryAndExitThread
0x1800059ee  int     3; Trap to Debugger
0x1800059ef  mov     rbx, [rsp+48h+arg_0]
0x1800059f4  xor     eax, eax
0x1800059f6  mov     rsi, [rsp+48h+arg_18]
0x1800059fb  add     rsp, 40h
0x1800059ff  pop     rdi
0x180005a00  retn
```
