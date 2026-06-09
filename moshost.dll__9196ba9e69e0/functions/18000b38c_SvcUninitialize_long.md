# SvcUninitialize(long)

- ea: `0x18000b38c`
- end: `0x18000b5fd`
- name: `?SvcUninitialize@@YAJJ@Z`
- size: `625`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000b720`
- `0x18000bcc0`

## callees

- `0x180001d00`
- `0x180006e20`
- `0x180007298`
- `0x18000b38c`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000b4ec`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000b4ec`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000b5b4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000b5b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b50a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b50a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b4cf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b4cf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b486`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b4f4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b486`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b4f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b465`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b4e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b465`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b4e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b5d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b5d7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000b475`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000b475`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b3f3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b3f3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b400`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b400`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000b47e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000b47e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b3e1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b3e1`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000b5c3`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000b5c3`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18000b453`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18000b453`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000b55d`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000b55d`
- `ZTrace_Maps!ZTraceReportIgnoreNoThis` at `0x18000b4c2`
- `ZTrace_Maps!ZTraceReportIgnoreNoThis` at `0x18000b576`
- `ZTrace_Maps!ZTraceReportIgnoreNoThis` at `0x18000b4c2`
- `ZTrace_Maps!ZTraceReportIgnoreNoThis` at `0x18000b576`

## string_xrefs

- `0x18000b554`: `MapsBackgroundTransferUnregisterComServer`
- `0x18000b43a`: `[MosHost] Service - Shutdown - SvcUninitialize - cause: 0x%08x`

## pseudocode

```c
__int64 __fastcall SvcUninitialize(int a1)
{
  PTP_TIMER v2; // rcx
  struct _TP_WORK *v3; // rdi
  DWORD LastError; // ebx
  int v5; // eax
  HMODULE v6; // rdi
  DWORD v7; // ebx
  LPVOID v8; // rcx
  int v9; // eax
  int v10; // eax
  HANDLE v11; // rcx
  _BYTE Context[16]; // [rsp+40h] [rbp-48h] BYREF
  HANDLE WaitHandle; // [rsp+50h] [rbp-38h]
  HANDLE hEvent; // [rsp+58h] [rbp-30h]
  struct _FILETIME pftDueTime; // [rsp+60h] [rbp-28h] BYREF

  ScopedWatchdogTimer::ScopedWatchdogTimer(
    Context,
    0x493E0u,
    (void (*)(void))ScopedWatchdogHandlers::MosHostServiceUninitialize_CrashOnTimerExpired);
  v2 = pti;
  if ( pti )
  {
    pftDueTime = 0;
    SetThreadpoolTimer(pti, &pftDueTime, 0, 0);
    WaitForThreadpoolTimerCallbacks(pti, 1);
    CloseThreadpoolTimer(pti);
    pti = 0;
  }
  if ( (Microsoft_Windows_MosHostEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v2, ServiceStop);
  ZTraceHelperNoThis(3, "SvcUninitialize", 401, "[MosHost] Service - Shutdown - SvcUninitialize - cause: 0x%08x", a1);
  v3 = pwk;
  if ( pwk )
  {
    LastError = GetLastError();
    WaitForThreadpoolWorkCallbacks(v3, 1);
    CloseThreadpoolWork(v3);
    SetLastError(LastError);
  }
  pwk = 0;
  if ( qword_1800185D0 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)qword_1800185D0 + 8LL))(qword_1800185D0);
    if ( v5 < 0 )
      ZTraceReportIgnoreNoThis(v5, "SvcUninitialize", 410);
  }
  EnterCriticalSection(&stru_1800186B0);
  v6 = hLibModule;
  if ( hLibModule )
  {
    v7 = GetLastError();
    FreeLibrary(v6);
    SetLastError(v7);
  }
  hLibModule = 0;
  LeaveCriticalSection(&stru_1800186B0);
  v8 = ppv;
  if ( ppv )
  {
    v9 = (*(__int64 (__fastcall **)(LPVOID, __int64 (__fastcall *)(), _QWORD, GUID *, int, _QWORD))(*(_QWORD *)ppv + 24LL))(
           ppv,
           UnregisterClassFactory,
           0,
           &IID_IContextCallback,
           5,
           0);
    if ( v9 < 0 )
    {
      v10 = ZTraceReportPropagationNoThis(v9, "MapsBackgroundTransferUnregisterComServer", 83);
      if ( v10 < 0 )
        ZTraceReportIgnoreNoThis(v10, "SvcUninitialize", 415);
      goto LABEL_19;
    }
    v8 = ppv;
  }
  if ( v8 )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 16LL))(v8);
  }
LABEL_19:
  v11 = hEvent;
  if ( hEvent )
  {
    if ( WaitHandle )
    {
      SetEvent(hEvent);
      UnregisterWaitEx(WaitHandle, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      WaitHandle = 0;
      v11 = hEvent;
    }
    CloseHandle(v11);
  }
  return 0;
}

```

## disassembly

```asm
0x18000b38c  mov     [rsp+arg_8], rbx
0x18000b391  push    rdi
0x18000b392  sub     rsp, 80h
0x18000b399  mov     rax, cs:__security_cookie
0x18000b3a0  xor     rax, rsp
0x18000b3a3  mov     [rsp+88h+var_18], rax
0x18000b3a8  mov     ebx, ecx
0x18000b3aa  lea     r8, ?MosHostServiceUninitialize_CrashOnTimerExpired@ScopedWatchdogHandlers@@YAXXZ; void (*)(void)
0x18000b3b1  mov     edx, 493E0h; unsigned int
0x18000b3b6  lea     rcx, [rsp+88h+Context]; Context
0x18000b3bb  call    ??0ScopedWatchdogTimer@@QEAA@KP6AXXZ@Z; ScopedWatchdogTimer::ScopedWatchdogTimer(ulong,void (*)(void))
0x18000b3c0  nop
0x18000b3c1  mov     rcx, cs:pti; pti
0x18000b3c8  test    rcx, rcx
0x18000b3cb  jz      short loc_18000B411
0x18000b3cd  mov     qword ptr [rsp+88h+pftDueTime.dwLowDateTime], 0
0x18000b3d6  xor     r9d, r9d; msWindowLength
0x18000b3d9  xor     r8d, r8d; msPeriod
0x18000b3dc  lea     rdx, [rsp+88h+pftDueTime]; pftDueTime
0x18000b3e1  call    cs:__imp_SetThreadpoolTimer
0x18000b3e7  mov     edx, 1; fCancelPendingCallbacks
0x18000b3ec  mov     rcx, cs:pti; pti
0x18000b3f3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000b3f9  mov     rcx, cs:pti; pti
0x18000b400  call    cs:__imp_CloseThreadpoolTimer
0x18000b406  mov     cs:pti, 0
0x18000b411  test    cs:Microsoft_Windows_MosHostEnableBits, 1
0x18000b418  jz      short loc_18000B436
0x18000b41a  lea     rax, [rsp+88h+pftDueTime]
0x18000b41f  mov     [rsp+88h+var_68], rax
0x18000b424  mov     r9d, 1
0x18000b42a  lea     rdx, ServiceStop
0x18000b431  call    McGenEventWrite_EventWriteTransfer
0x18000b436  mov     dword ptr [rsp+88h+var_68], ebx
0x18000b43a  lea     r9, aMoshostService_2; "[MosHost] Service - Shutdown - SvcUnini"...
0x18000b441  mov     r8d, 191h
0x18000b447  lea     rdx, aSvcuninitializ; "SvcUninitialize"
0x18000b44e  mov     ecx, 3
0x18000b453  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x18000b459  mov     rdi, cs:pwk
0x18000b460  test    rdi, rdi
0x18000b463  jz      short loc_18000B48C
0x18000b465  call    cs:__imp_GetLastError
0x18000b46b  mov     ebx, eax
0x18000b46d  mov     edx, 1; fCancelPendingCallbacks
0x18000b472  mov     rcx, rdi; pwk
0x18000b475  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18000b47b  mov     rcx, rdi; pwk
0x18000b47e  call    cs:__imp_CloseThreadpoolWork
0x18000b484  mov     ecx, ebx; dwErrCode
0x18000b486  call    cs:__imp_SetLastError
0x18000b48c  mov     cs:pwk, 0
0x18000b497  mov     rcx, cs:qword_1800185D0
0x18000b49e  test    rcx, rcx
0x18000b4a1  jz      short loc_18000B4C8
0x18000b4a3  mov     rax, [rcx]
0x18000b4a6  mov     rax, [rax+8]
0x18000b4aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4af  test    eax, eax
0x18000b4b1  jns     short loc_18000B4C8
0x18000b4b3  mov     r8d, 19Ah
0x18000b4b9  lea     rdx, aSvcuninitializ; "SvcUninitialize"
0x18000b4c0  mov     ecx, eax
0x18000b4c2  call    cs:__imp_?ZTraceReportIgnoreNoThis@@YAXHPEBDH@Z; ZTraceReportIgnoreNoThis(int,char const *,int)
0x18000b4c8  lea     rcx, stru_1800186B0; lpCriticalSection
0x18000b4cf  call    cs:__imp_EnterCriticalSection
0x18000b4d5  mov     rdi, cs:hLibModule
0x18000b4dc  test    rdi, rdi
0x18000b4df  jz      short loc_18000B4FA
0x18000b4e1  call    cs:__imp_GetLastError
0x18000b4e7  mov     ebx, eax
0x18000b4e9  mov     rcx, rdi; hLibModule
0x18000b4ec  call    cs:__imp_FreeLibrary
0x18000b4f2  mov     ecx, ebx; dwErrCode
0x18000b4f4  call    cs:__imp_SetLastError
0x18000b4fa  xor     eax, eax
0x18000b4fc  mov     cs:hLibModule, rax
0x18000b503  lea     rcx, stru_1800186B0; lpCriticalSection
0x18000b50a  call    cs:__imp_LeaveCriticalSection
0x18000b510  mov     rcx, cs:ppv
0x18000b517  test    rcx, rcx
0x18000b51a  jz      short loc_18000B585
0x18000b51c  mov     rax, [rcx]
0x18000b51f  mov     [rsp+88h+var_60], 0
0x18000b528  mov     dword ptr [rsp+88h+var_68], 5
0x18000b530  lea     r9, IID_IContextCallback
0x18000b537  xor     r8d, r8d
0x18000b53a  lea     rdx, UnregisterClassFactory
0x18000b541  mov     rax, [rax+18h]
0x18000b545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b54a  test    eax, eax
0x18000b54c  jns     short loc_18000B57E
0x18000b54e  mov     r8d, 53h ; 'S'
0x18000b554  lea     rdx, aMapsbackground; "MapsBackgroundTransferUnregisterComServ"...
0x18000b55b  mov     ecx, eax
0x18000b55d  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000b563  test    eax, eax
0x18000b565  jns     short loc_18000B5A2
0x18000b567  mov     r8d, 19Fh
0x18000b56d  lea     rdx, aSvcuninitializ; "SvcUninitialize"
0x18000b574  mov     ecx, eax
0x18000b576  call    cs:__imp_?ZTraceReportIgnoreNoThis@@YAXHPEBDH@Z; ZTraceReportIgnoreNoThis(int,char const *,int)
0x18000b57c  jmp     short loc_18000B5A2
0x18000b57e  mov     rcx, cs:ppv
0x18000b585  test    rcx, rcx
0x18000b588  jz      short loc_18000B5A2
0x18000b58a  mov     cs:ppv, 0
0x18000b595  mov     rax, [rcx]
0x18000b598  mov     rax, [rax+10h]
0x18000b59c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5a1  nop
0x18000b5a2  mov     rcx, [rsp+88h+hEvent]; hEvent
0x18000b5a7  test    rcx, rcx
0x18000b5aa  jz      short loc_18000B5DD
0x18000b5ac  cmp     [rsp+88h+WaitHandle], 0
0x18000b5b2  jz      short loc_18000B5D7
0x18000b5b4  call    cs:__imp_SetEvent
0x18000b5ba  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18000b5be  mov     rcx, [rsp+88h+WaitHandle]; WaitHandle
0x18000b5c3  call    cs:__imp_UnregisterWaitEx
0x18000b5c9  mov     [rsp+88h+WaitHandle], 0
0x18000b5d2  mov     rcx, [rsp+88h+hEvent]; hObject
0x18000b5d7  call    cs:__imp_CloseHandle
0x18000b5dd  xor     eax, eax
0x18000b5df  mov     rcx, [rsp+88h+var_18]
0x18000b5e4  xor     rcx, rsp; StackCookie
0x18000b5e7  call    __security_check_cookie
0x18000b5ec  mov     rbx, [rsp+88h+arg_8]
0x18000b5f4  add     rsp, 80h
0x18000b5fb  pop     rdi
0x18000b5fc  retn
```
