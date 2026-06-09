# CreatePortThread

- ea: `0x1800880a0`
- end: `0x18008821a`
- name: `CreatePortThread`
- size: `378`
- prototype: `__int64 __fastcall(LPVOID lpParameter)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180006d7c`

## callees

- `0x180008520`
- `0x180008560`
- `0x1800086e0`
- `0x180008730`
- `0x18003ea2c`
- `0x180054638`
- `0x1800880a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18008817a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18008817a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800880db`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800880ef`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800880db`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800880ef`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800881e5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800881e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800881ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800881ae`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18008812f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18008812f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800881a4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800881a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088150`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088166`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088150`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088166`

## string_xrefs

- `0x1800881b7`: `Failed to set port thread priority.  Error %d`
- `0x180088184`: `Failed to create port thread for port '%ws'.`
- `0x18008818b`: `CreatePortThread`
- `0x1800881be`: `CreatePortThread`

## pseudocode

```c
__int64 __fastcall CreatePortThread(LPVOID lpParameter, __int64 a2)
{
  bool v2; // zf
  HANDLE EventW; // rax
  HANDLE Thread; // rax
  void *v6; // rcx
  unsigned int v7; // edi
  void *v8; // rcx
  void *v9; // rcx
  DWORD LastError; // eax
  __int64 v12; // rcx
  __int64 ThreadId; // [rsp+48h] [rbp+10h] BYREF

  ThreadId = a2;
  v2 = (*((_DWORD *)lpParameter + 12) & 0x400000) == 0;
  LODWORD(ThreadId) = 0;
  if ( v2 && (*((_BYTE *)lpParameter + 48) & 8) == 0 )
  {
    *((_QWORD *)lpParameter + 8) = CreateEventW(0, 0, 0, 0);
    EventW = CreateEventW(0, 0, 0, 0);
    v2 = *((_QWORD *)lpParameter + 8) == 0;
    *((_QWORD *)lpParameter + 22) = EventW;
    if ( !v2 && EventW )
    {
      *((_DWORD *)lpParameter + 12) |= 4u;
      Thread = CreateThread(0, 0x8000u, (LPTHREAD_START_ROUTINE)PortThread, lpParameter, 0, (LPDWORD)&ThreadId);
      *((_QWORD *)lpParameter + 23) = Thread;
      if ( Thread )
      {
        if ( !SetThreadPriority(Thread, *(int *)&dwPortThreadPriority) )
        {
          LastError = GetLastError();
          LocalSpoolerTelemetry::WriteDbgTraceWarning(
            "CreatePortThread",
            L"Failed to set port thread priority.  Error %d",
            LastError);
        }
        SafeIncrementReference((unsigned int *)lpParameter + 4);
        LeaveSplSem(v12);
        WaitForSingleObject(*((HANDLE *)lpParameter + 22), 0xFFFFFFFF);
        EnterSplSem(0);
        if ( *((_DWORD *)lpParameter + 4) )
          SafeDecrementReference((unsigned int *)lpParameter + 4);
        *((_DWORD *)lpParameter + 12) |= 8u;
        return 1;
      }
      *((_DWORD *)lpParameter + 12) &= ~4u;
    }
    v6 = (void *)*((_QWORD *)lpParameter + 8);
    v7 = 0;
    if ( v6 )
    {
      CloseHandle(v6);
      *((_QWORD *)lpParameter + 8) = 0;
    }
    v8 = (void *)*((_QWORD *)lpParameter + 22);
    if ( v8 )
    {
      CloseHandle(v8);
      v9 = (void *)*((_QWORD *)lpParameter + 28);
      *((_QWORD *)lpParameter + 22) = 0;
      SetEvent(v9);
    }
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "CreatePortThread",
      L"Failed to create port thread for port '%ws'.",
      *((_QWORD *)lpParameter + 3));
    return v7;
  }
  return 1;
}

```

## disassembly

```asm
0x1800880a0  mov     [rsp+arg_0], rbx
0x1800880a5  mov     [rsp+ThreadId], rdx
0x1800880aa  push    rdi
0x1800880ab  sub     rsp, 30h
0x1800880af  test    dword ptr [rcx+30h], 400000h
0x1800880b6  mov     rbx, rcx
0x1800880b9  mov     dword ptr [rsp+38h+ThreadId], 0
0x1800880c1  jnz     loc_18008820A
0x1800880c7  test    byte ptr [rcx+30h], 8
0x1800880cb  jnz     loc_18008820A
0x1800880d1  xor     r9d, r9d; lpName
0x1800880d4  xor     r8d, r8d; bInitialState
0x1800880d7  xor     edx, edx; bManualReset
0x1800880d9  xor     ecx, ecx; lpEventAttributes
0x1800880db  call    cs:__imp_CreateEventW
0x1800880e1  xor     r9d, r9d; lpName
0x1800880e4  xor     r8d, r8d; bInitialState
0x1800880e7  xor     edx, edx; bManualReset
0x1800880e9  mov     [rbx+40h], rax
0x1800880ed  xor     ecx, ecx; lpEventAttributes
0x1800880ef  call    cs:__imp_CreateEventW
0x1800880f5  cmp     qword ptr [rbx+40h], 0
0x1800880fa  mov     [rbx+0B0h], rax
0x180088101  jz      short loc_180088145
0x180088103  test    rax, rax
0x180088106  jz      short loc_180088145
0x180088108  or      dword ptr [rbx+30h], 4
0x18008810c  lea     rax, [rsp+38h+ThreadId]
0x180088111  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x180088116  lea     r8, PortThread; lpStartAddress
0x18008811d  mov     r9, rbx; lpParameter
0x180088120  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x180088128  mov     edx, 8000h; dwStackSize
0x18008812d  xor     ecx, ecx; lpThreadAttributes
0x18008812f  call    cs:__imp_CreateThread
0x180088135  mov     [rbx+0B8h], rax
0x18008813c  test    rax, rax
0x18008813f  jnz     short loc_18008819B
0x180088141  and     dword ptr [rbx+30h], 0FFFFFFFBh
0x180088145  mov     rcx, [rbx+40h]; hObject
0x180088149  xor     edi, edi
0x18008814b  test    rcx, rcx
0x18008814e  jz      short loc_18008815A
0x180088150  call    cs:__imp_CloseHandle
0x180088156  mov     [rbx+40h], rdi
0x18008815a  mov     rcx, [rbx+0B0h]; hObject
0x180088161  test    rcx, rcx
0x180088164  jz      short loc_180088180
0x180088166  call    cs:__imp_CloseHandle
0x18008816c  mov     rcx, [rbx+0E0h]; hEvent
0x180088173  mov     [rbx+0B0h], rdi
0x18008817a  call    cs:__imp_SetEvent
0x180088180  mov     r8, [rbx+18h]
0x180088184  lea     rdx, aFailedToCreate_0; "Failed to create port thread for port '"...
0x18008818b  lea     rcx, aCreateportthre; "CreatePortThread"
0x180088192  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180088197  mov     eax, edi
0x180088199  jmp     short loc_18008820F
0x18008819b  mov     edx, cs:dwPortThreadPriority; nPriority
0x1800881a1  mov     rcx, rax; hThread
0x1800881a4  call    cs:__imp_SetThreadPriority
0x1800881aa  test    eax, eax
0x1800881ac  jnz     short loc_1800881CA
0x1800881ae  call    cs:__imp_GetLastError
0x1800881b4  mov     r8d, eax
0x1800881b7  lea     rdx, aFailedToSetPor; "Failed to set port thread priority.  Er"...
0x1800881be  lea     rcx, aCreateportthre; "CreatePortThread"
0x1800881c5  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800881ca  lea     rdi, [rbx+10h]
0x1800881ce  mov     rcx, rdi; unsigned int *
0x1800881d1  call    ?SafeIncrementReference@@YAKPEAK@Z; SafeIncrementReference(ulong *)
0x1800881d6  call    LeaveSplSem
0x1800881db  mov     rcx, [rbx+0B0h]; hHandle
0x1800881e2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800881e5  call    cs:__imp_WaitForSingleObject
0x1800881eb  xor     ecx, ecx
0x1800881ed  call    EnterSplSem
0x1800881f2  cmp     dword ptr [rdi], 0
0x1800881f5  jz      short loc_1800881FF
0x1800881f7  mov     rcx, rdi; unsigned int *
0x1800881fa  call    ?SafeDecrementReference@@YAKPEAK@Z; SafeDecrementReference(ulong *)
0x1800881ff  or      dword ptr [rbx+30h], 8
0x180088203  mov     edi, 1
0x180088208  jmp     short loc_180088197
0x18008820a  mov     eax, 1
0x18008820f  mov     rbx, [rsp+38h+arg_0]
0x180088214  add     rsp, 30h
0x180088218  pop     rdi
0x180088219  retn
```
